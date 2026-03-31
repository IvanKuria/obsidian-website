---
title: "8-Week Plan"
type: reference
draft: true
tags:
  - personal
---

**Start:** March 24  
**End:** May 18  
**Goal:** Brush up on React & backend, learn cloud fundamentals, and understand DataStage & ETL workflows.

---

## ✅ Week 1–2: Deepen React + Modern Patterns

### 🎯 Goals
- Refactor component structure using best practices
- Practice hooks, context, and React testing

### 📚 Topics
- [ ] Custom Hooks
- [ ] Context API for global state
- [ ] Error boundaries
- [ ] Component patterns (container/presentational, compound)
- [ ] Unit testing with Jest + React Testing Library

### 🛠️ Mini Project
- [ ] Build a **Task Manager App**
  - [ ] Add Firebase Auth for user login
  - [ ] Use custom hooks for state management
  - [ ] Test components with Jest

### 🔗 Resources
- [ ] [React Docs – Advanced Guides](https://reactjs.org/docs/hooks-intro.html)
- [ ] [useHooks](https://usehooks.com/)
- [ ] Kent C. Dodds’ Blog

---

## ✅ Week 3: Backend – Express.js + REST API Mastery

### 🎯 Goals
- Build and test robust REST APIs
- Master routing, middleware, and authentication

### 📚 Topics
- [ ] Express routing and middleware
- [ ] RESTful design principles
- [ ] Error handling and status codes
- [ ] JWT Authentication
- [ ] PostgreSQL integration (via Prisma or Sequelize)

### 🛠️ Mini Project
- [ ] Build a **Book Store API** with:
  - [ ] CRUD operations for books
  - [ ] JWT-based user auth

### 🔗 Resources
- [ ] [Backend Developer Roadmap](https://roadmap.sh/backend)

---

## ✅ Week 4: Databases – PostgreSQL & IBM Db2

### 🎯 Goals
- Get comfortable with relational databases
- Understand Db2 basics for IBM tooling

### 📚 Topics
- [ ] SQL basics, joins, indexes
- [ ] Schema design
- [ ] ORM usage (Prisma or Sequelize)
- [ ] Explore IBM Db2 on [IBM Cloud Lite](https://www.ibm.com/cloud/free)

### 🛠️ Challenge
- [ ] Refactor **Grocery Tracker App** to use PostgreSQL backend

### 🔗 Resources
- [ ] [SQLBolt Tutorial](https://sqlbolt.com/)
- [ ] IBM Db2 Documentation

---

## ✅ Week 5: Cloud 101 – IBM Cloud + AWS Basics

### 🎯 Goals
- Understand core cloud services and deployments
- Get comfortable with cloud app hosting

### 📚 Topics
- [ ] IaaS vs PaaS vs SaaS
- [ ] IBM Cloud Functions, Code Engine, Db2 setup
- [ ] AWS EC2, S3 basics (just for comparison)
- [ ] CI/CD with GitHub Actions

### 🛠️ Task
- [ ] Deploy your React + Express app to IBM Cloud or Render.com

### 🔗 Resources
- [ ] [IBM Cloud Docs](https://cloud.ibm.com/docs)
- [ ] [IBM Cloud Training](https://www.ibm.com/training/cloud)

---

## ✅ Week 6: ETL Concepts + Intro to DataStage

### 🎯 Goals
- Grasp ETL pipeline basics
- Understand what DataStage does

### 📚 Topics
- [ ] What is ETL/ELT
- [ ] Data pipeline components (Extract → Transform → Load)
- [ ] Parallelism and job types in DataStage
- [ ] DataStage architecture

### 🛠️ Task
- [ ] Build a simple **ETL script in Python**
  - [ ] Extract data from CSV
  - [ ] Clean & transform
  - [ ] Load into PostgreSQL

### 🔗 Resources
- [ ] [IBM DataStage Product Page](https://www.ibm.com/products/datastage)
- [ ] [ETL Concepts (Guru99)](https://www.guru99.com/etl-testing.html)

---

## ✅ Week 7: Microservices + API Gateway Concepts

### 🎯 Goals
- Learn microservice structure and API integration

### 📚 Topics
- [ ] Microservices vs monoliths
- [ ] REST vs gRPC (high-level)
- [ ] API Gateway concepts (e.g., IBM API Connect)
- [ ] Rate limiting and service auth
- [ ] Event-driven overview (Kafka/RabbitMQ basics)

### 🛠️ Task
- [ ] Split Book Store API:
  - [ ] Auth service
  - [ ] Book service

### 🔗 Resources
- [ ] [Microservices.io](https://microservices.io/)

---

## ✅ Week 8: Final Project – School Inventory Manager (Full Stack)

### 🎯 Goal
Build a full-stack app that simulates a real-world DataStage-like workflow in a school setting.

### 🛠️ Features
- [ ] React frontend with reusable components
- [ ] Express.js backend with PostgreSQL
- [ ] Firebase Auth (or JWT)
- [ ] Inventory dashboard with:
  - [ ] Add/View/Edit/Delete school items
  - [ ] Track quantity and expiration (e.g., lab equipment, supplies)
  - [ ] Low stock alerts
- [ ] Simple ETL logic:
  - [ ] Nightly script checks for low stock or expired items
  - [ ] Sends alerts or logs into a separate table
- [ ] Deployment to IBM Cloud or Render

### 🔗 Bonus Learning
- [ ] Read case studies of DataStage in data warehousing
- [ ] Check out IBM Developer Blog for examples
- [ ] Browse IBM Redbooks for ETL and integration best practices

---

# 🚀 You're ready for IBM!