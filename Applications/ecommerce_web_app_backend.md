# 🛒 E-commerce Backend (2025 Edition)  
*Node.js Backend with Raw SQL & Sequelize ORM Implementations*  

![Node.js](https://img.shields.io/badge/Node.js-20-green)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue)
![Sequelize](https://img.shields.io/badge/Sequelize-7.0-orange)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue)

A dual-implementation backend system demonstrating:
1. **Raw SQL** with `pg` library  
2. **ORM** with Sequelize  
 
Built with modern security practices, TypeScript, and AI-ready architecture.

---

## 🚀 Features  
**2025-Ready Architecture**  
- JWT Authentication with refresh tokens  
- Role-based access control (RBAC)  
- AI-powered search (vector similarity)  
- Email microservice with queueing  
- Rate limiting & SQL injection protection  

**Core Functionality**  
- Admin Dashboard (EJS Templates)  
- Product Catalog System  
- Favorites Management  
- Contact Admin Portal  
- Automated API Documentation  

---

## 📦 Database Schema (2025 Optimized)  

```sql
-- Modern schema with vector search support
CREATE TABLE users (
  id UUID PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password_hash TEXT NOT NULL,
  is_admin BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMPTZ DEFAULT NOW(),
  search_vector TSVECTOR -- For AI-powered search
);

CREATE TABLE products (
  id UUID PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  description TEXT,
  price DECIMAL(10,2) CHECK (price > 0),
  category_id UUID REFERENCES categories(id),
  subcategory_id UUID REFERENCES subcategories(id),
  embedding VECTOR(1536) -- For AI similarity search
);
```

## 🌐 API Endpoints  

### 🔒 Authentication  
| Method | Endpoint | Description | Access |
|--------|---------|-------------|--------|
| POST | /auth/signup | User registration | Public |
| POST | /auth/login | Login with JWT | Public |
| POST | /auth/refresh | Refresh JWT token | Private |

### 📦 Product Management (Admin)  
```http
POST /admin/products
Content-Type: application/json
Authorization: Bearer <ADMIN_JWT>

{
  "name": "Quantum Laptop 2025",
  "price": 2999.99,
  "description": "AI-optimized laptop with neural processor",
  "category": "Electronics",
  "subcategory": "Laptops"
}
```

### 🔍 User Features  
- `GET /products/search?q=quantum&maxPrice=3000` - Hybrid search (text + vector)  
- `POST /products/:id/favorite` - Add to favorites  
- `GET /products/favorites` - Get user favorites  
- `POST /support` - Contact admin with AI-sorted priority  

---

## 🛠️ Tech Stack  

| Category | Tools |
|----------|-------|
| **Runtime** | Node.js 20 (ESM modules) |
| **Language** | TypeScript 5.0 |
| **Database** | PostgreSQL 16 + pgvector |
| **ORM** | Sequelize 7.0 + TypeScript decorators |
| **Auth** | JWT + refresh token rotation |
| **Search** | pgvector + OpenAI embeddings |
| **Email** | Resend API + BullMQ queue |

---

## ⚙️ Setup  

### 1. Clone & Install  
```bash
git clone https://github.com/yourrepo/ecommerce-2025.git
cd ecommerce-2025
pnpm install  # 2025 recommended package manager
```

### 2. Database Setup  
```bash
# Using Docker Compose v3
docker compose up -d postgres redis

# Run migrations
pnpm migrate:raw   # Raw SQL version
pnpm migrate:orm   # Sequelize version
```

### 3. Environment Configuration  
```env
# .env file
AI_SEARCH_KEY="sk-your-openai-key" 
DB_URL="postgres://user:pass@localhost:5432/ecommerce"
JWT_SECRET="your_quantum-resistant_secret"
```

### 4. Start Servers  
```bash
# Raw SQL implementation
pnpm start:raw

# Sequelize implementation
pnpm start:orm
```

---

## 🔐 Security Best Practices  

### SQL Injection Protection  
```typescript
// Raw SQL example with parameterization
const result = await pool.query(
  'SELECT * FROM products WHERE price > $1',
  [maxPrice]
);
```

### Rate Limiting  
```typescript
app.use(rateLimit({
  windowMs: 15 * 60 * 1000, // 15 minutes
  max: 100 // Limit each IP to 100 requests per window
}));
```

### JWT Validation  
```typescript
interface JwtPayload {
  userId: string;
  isAdmin: boolean;
  refreshTokenId?: string;
}
```

---

## 📊 Testing Strategy  

1. **API Testing (Postman)**  
2. **Unit Tests**  
```bash
pnpm test:cov # 90% coverage required
```
3. **Load Testing**  
```bash
artillery run load-test.yml
```

---

## 🚢 Deployment  

### Docker Production Setup  
```dockerfile
# 2025 Multi-stage build
FROM node:20-slim as base
ENV NODE_ENV=production
EXPOSE 3000

FROM base as prod
COPY --chown=node:node . .
RUN pnpm install --frozen-lockfile
CMD ["node", "dist/app.js"]
```

---

## 📚 Documentation  

### Interactive API Docs  
Access Swagger UI at `http://localhost:3000/docs`  

### EJS Templates  
```ejs
<!-- Admin Dashboard -->
<% if (user.isAdmin) { %>
  <button class="ai-search-btn" 
          data-vector="<%= product.embedding %>">
    Find Similar
  </button>
<% } %>
```

---

## 🌟 Future Roadmap  

- AI-powered product recommendations  
- Blockchain-based order verification  
- AR product preview integration  
- Quantum-safe cryptography migration  

---

## 🚀 Key Improvements for 2025  

1. **Added AI/ML integrations** (vector search, recommendations)  
2. **Modern security practices** (refresh tokens, rate limiting)  
3. **TypeScript-first architecture**  
4. **Hybrid raw SQL/ORM implementation guide**  
5. **Deployment-ready Docker configuration**  
6. **Future-proof database schema**  
7. **Interactive API documentation**  
8. **Performance optimization strategies**  

---
