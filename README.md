# odoo-k8s-AllInOne
Odoo and Postgres working in namespace pre-production

## How to run
### 1- Create namespace
<code>kubectl create namespace pre-production</code>

### 2- Initialize odoo database
<code>kubectl --namespace pre-production apply -f initialize.yml</code>
#### Wait until odoo-pod-init running
<code>watch kubectl --namespace pre-production get pod</code>
#### Setup odoo
<p>Go to browser, enter odoo link and create database <code>odoo-db</code> and make sure login match login in odoo-postgres.yml</p>
<p>After create we don't need theese pods</p>

### 3- Delete initialize.yml
<code>kubectl --namespace pre-production delete -f initialize.yml</code>

### 4- Create final odoo pod
<code>kubectl --namespace pre-production apply -f odoo-postgres.yml</code>

### Enjoy :)

