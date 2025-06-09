
---

### **1. Project Overview**
> A dashboard-style Vue.js app to showcase my development portfolio. Includes a profile, project showcase, contact form, and a creative page with a random quote generator.

---

### **2. Features**

#### 🔐 Login Page
- Simple login with hardcoded username/password (`admin / password`)
- Redirects to dashboard after successful login

#### 👤 Profile Page
- Profile image and description
- GitHub and LinkedIn social buttons

#### 💼 Portfolio Showcase
- Project cards with titles, descriptions, and links
- Responsive and visually appealing layout

#### ✉️ Contact Page
- Form with validation
- Card layout with an illustrative image on the side

#### 🎨 Creative Page
- Two-column layout: quote generator and image
- Theme toggle (light/dark mode)
- Dynamic quote generation

---

### **3. Creative Page Description**
> The creative page features a motivational quote generator. It’s intended to provide inspiration and mental clarity for both users and developers. Built with a clean two-column design and theme switching for customization.

---

### **4. Screenshots**

Insert full screenshots of:

- Login Page  
- Profile Page  
- Portfolio Showcase  
- Contact Page  
- Creative Page  

---

### **5. Technologies Used**
- Vue.js 3  
- Vue Router  
- Bootstrap 5  
- Node.js & NPM  
- Git & GitHub  

---

### **6. Challenges & Solutions**

| Challenge                          | Solution                                                                 |
|-----------------------------------|--------------------------------------------------------------------------|
| Vue Router redirect after login   | Used programmatic navigation via `$router.push('/portfolio/profile')`   |
| Contact form validation           | Used `v-model` with required fields and conditionally shown success alert |
| Layout alignment issues           | Leveraged Bootstrap’s grid and utility classes like `h-100`, `align-items-center` |
| Making quote generator dynamic    | Used array of strings and `Math.random()` to display a different quote each time |

