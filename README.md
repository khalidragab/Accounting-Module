# Secure Accounting ERP Foundation

This package replaces public browser-only storage with Supabase Authentication and PostgreSQL tables.

## Setup
1. Create a Supabase project.
2. Run `supabase/migrations/002_secure_erp.sql` in SQL Editor.
3. Create the first administrator in Authentication > Users.
4. Add that user's row to `user_profiles` with a generated `USR-2026-xxxxxx` code and ADMIN role.
5. Update `config/supabase-config.js` with the project URL and publishable anon key.
6. Upload to GitHub Pages.

Never use a Supabase service-role key in frontend code. The publishable key is protected by Authentication and RLS.

All ERP business records use database-generated read-only codes: Customer Code, Supplier Code, Bank Account Code, Invoice Code, Receipt Code, AP Invoice Code, Refund Code, Journal Code and Approval Code.
