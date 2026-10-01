Primeiro execute o SQL presente em <code_sql></code_sql> para criar o backend do projeto, depois execute tudo o que está descrito em <prompt_construcao></prompt_construcao>. Anexei junto deste prompt o sprint e o mapa de navegação do app Tudo Para Mulheres para que possa se basear e criar a solução com mais clareza e assertividade.

<code_sql>

-- =========================================================
-- EXTENSÃO NECESSÁRIA
-- =========================================================
create extension if not exists pgcrypto;

-- =========================================================
-- CATEGORIAS
-- =========================================================
create table if not exists categories (
  id uuid primary key default gen_random_uuid(),
  name text
);

insert into categories (name)
values
  ('Cabelo'),
  ('Manicure'),
  ('Pedicure'),
  ('Maquiagem'),
  ('Sobrancelhas'),
  ('Unhas')
on conflict do nothing;

-- =========================================================
-- USERS
-- =========================================================
create table if not exists users (
  id uuid primary key default gen_random_uuid(),
  role text check (role in ('cliente', 'profissional')),
  nome text,
  nome_profissional text,
  email text unique,
  telefone text,
  cidade text,
  bairro text,
  endereco text,
  data_nascimento date,
  descricao_profissional text,
  experiencia text,
  atende_domicilio boolean default true,
  status_perfil text default 'ativo',
  created_at timestamp default now()
);

-- =========================================================
-- SERVICES
-- =========================================================
create table if not exists services (
  id uuid primary key default gen_random_uuid(),
  profissional_id uuid references users(id) on delete cascade,
  nome text,
  descricao text,
  preco numeric,
  duracao_minutos integer,
  observacoes text,
  created_at timestamp default now()
);

-- =========================================================
-- PORTFOLIOS
-- =========================================================
create table if not exists portfolios (
  id uuid primary key default gen_random_uuid(),
  profissional_id uuid references users(id) on delete cascade,
  image_url text,
  created_at timestamp default now()
);

-- =========================================================
-- BOOKINGS
-- =========================================================
create table if not exists bookings (
  id uuid primary key default gen_random_uuid(),
  cliente_id uuid references users(id),
  profissional_id uuid references users(id),
  service_id uuid references services(id),
  data date,
  horario time,
  endereco text,
  observacoes text,
  valor numeric,
  status text check (
    status in ('solicitado', 'aceito', 'recusado', 'cancelado', 'concluido')
  ) default 'solicitado',
  created_at timestamp default now()
);

-- =========================================================
-- REVIEWS
-- =========================================================
create table if not exists reviews (
  id uuid primary key default gen_random_uuid(),
  cliente_id uuid references users(id),
  profissional_id uuid references users(id),
  booking_id uuid references bookings(id),
  rating integer check (rating between 1 and 5),
  comentario text,
  created_at timestamp default now()
);

-- =========================================================
-- FAVORITES
-- =========================================================
create table if not exists favorites (
  id uuid primary key default gen_random_uuid(),
  cliente_id uuid references users(id),
  profissional_id uuid references users(id),
  created_at timestamp default now()
);

-- =========================================================
-- MESSAGES
-- =========================================================
create table if not exists messages (
  id uuid primary key default gen_random_uuid(),
  booking_id uuid references bookings(id),
  sender_id uuid references users(id),
  message text,
  image_url text,
  created_at timestamp default now()
);

</code_sql>

<prompt_construcao>

Create a mobile marketplace app called:

Tudo Para Mulheres

The app connects women looking for beauty services at home with professionals who provide those services.

This is similar to Uber / Airbnb but focused on beauty homecare services.

The first version (V1) must focus only on the marketplace core.

Do NOT implement:

- blog
- e-commerce
- AI concierge
- premium subscriptions
- content feeds

The goal of V1 is to support:

user registration → discovery → professional profile → service booking → appointment management → review system

--------------------------------

APP STRUCTURE

The system has two user roles:

1 CLIENT
2 PROFESSIONAL

After login the system must detect the role and redirect to the correct dashboard.

--------------------------------

DATABASE ENTITIES

Users
Services
Bookings
Reviews
Favorites
Portfolio
Messages

--------------------------------

USER TYPE: CLIENT

Fields

id
name
birthdate
phone
email
password
city
neighborhood
address

Features

search professionals
favorite professionals
book services
chat with professionals
leave reviews
manage bookings

--------------------------------

USER TYPE: PROFESSIONAL

Fields

id
name
professional_name
phone
email
city
neighborhood
description
experience
home_service_available
service_regions
availability_days
availability_hours
profile_status

Features

create services
upload portfolio
receive bookings
accept or reject bookings
manage agenda
chat with clients

--------------------------------

ENTITY: SERVICE

Fields

id
professional_id
name
description
price
duration_minutes
notes

Each professional can create multiple services.

--------------------------------

ENTITY: BOOKING

Fields

id
client_id
professional_id
service_id
date
time
address
notes
value
status

Possible status

requested
accepted
rejected
cancelled
completed

--------------------------------

ENTITY: REVIEW

Fields

id
client_id
professional_id
booking_id
rating
comment

Reviews can only be created after booking status = completed.

--------------------------------

MAIN SCREENS

Splash Screen

Show Tudo Para Mulheres logo
Subtitle

"Beleza onde você estiver"

After a few seconds navigate to welcome screen.

--------------------------------

WELCOME SCREEN

Elements

Logo
Title: Tudo Para Mulheres

Buttons

Login
Create account
Offer my services

Navigation

Login → login screen
Create account → client signup
Offer services → professional signup

--------------------------------

LOGIN

Fields

email or phone
password

Buttons

Login
Continue with Google
Forgot password

After login redirect based on role.

--------------------------------

CLIENT HOME

Elements

search bar
categories
featured professionals
nearby professionals

Categories

Hair
Manicure
Pedicure
Makeup
Eyebrows
Nails
All

Bottom navigation

Home
Search
Bookings
Favorites
Profile

--------------------------------

SEARCH SCREEN

Filters

service
neighborhood
price range
rating
availability today
weekend availability

Sorting

nearest
best rated
lowest price

Professional card shows

photo
professional name
services
rating
neighborhood
starting price

Button

View profile

--------------------------------

PROFESSIONAL PROFILE

Elements

profile photo
professional name
rating
description
services
portfolio
service regions
available schedule

Buttons

Favorite
Request booking
Send message

--------------------------------

BOOK SERVICE

Fields

service
date
time
address
notes
payment method

Button

Send request

Initial status

requested

--------------------------------

CLIENT BOOKINGS

Tabs

Pending
Confirmed
Completed
Cancelled

Each booking shows

professional
service
date
time
status

--------------------------------

CHAT

Simple messaging between client and professional.

Functions

text messages
image upload

--------------------------------

PROFESSIONAL DASHBOARD

Elements

daily summary
pending requests
today agenda
services

Bottom navigation

Home
Requests
Agenda
Portfolio
Profile

--------------------------------

PROFESSIONAL REQUESTS

Tabs

New
Accepted
Rejected
Completed

Actions

Accept
Reject
View details

--------------------------------

PROFESSIONAL AGENDA

Views

Today
Week
Month

--------------------------------

BUSINESS RULES

Client can only book if account exists.

Professional appears in search only if

profile complete
at least one service created
service region defined
profile active

Reviews allowed only after completed bookings.

--------------------------------

MVP GOAL

Create a fully functional marketplace including

authentication
role separation
professional discovery
service profiles
booking requests
booking management
agenda
chat
reviews

</prompt_construcao>