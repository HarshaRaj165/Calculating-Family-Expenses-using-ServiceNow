# 🏠 Calculating Family Expenses Using ServiceNow

## 📌 Overview
This project demonstrates the creation of a **custom ServiceNow application** that allows users to **log, track, and calculate family expenses** using ServiceNow’s low-code development environment.  
It is designed to showcase **custom table creation, form design, business rules, client scripts, and reporting capabilities** in ServiceNow.

---

## 🎯 Project Objectives
- Provide a centralized platform to record family expenses.
- Automatically calculate total monthly and category-wise expenses.
- Present the expense data in a user-friendly and visual way.
- Demonstrate ServiceNow’s **low-code app development capabilities** for beginners.

---

##  Key Features

- Custom table `Family Expenses` to store expense records with details like category, amount, date, and description.
- Data entry form enabling quick addition of expenses with mandatory validation.
- Expense calculation logic to compute total and categorized spending.
- Simple reporting or dashboard widgets to visualize monthly or category-wise spending.

---

## 🛠 Tools & Technologies Used
- **ServiceNow Personal Developer Instance (PDI)**
- **Custom Tables** – for storing expense records.
- **Form Layout Configuration** – to create user-friendly input forms.
- **Client Scripts (JavaScript)** – for form validations and dynamic field behavior.
- **Business Rules** – to calculate totals automatically.
- **Reports & Dashboards** – for visualizing spending patterns.
- **UI Actions** – to trigger calculations or navigation.

---

## 🏗 Features Implemented
1. **Custom Table: `u_family_expenses`**
   - Fields: Expense Category, Amount, Date, Description, Payment Mode.
   - Created in **System Definition → Tables**.

2. **Form Layout & Sections**
   - Arranged fields in sections like **Basic Info** and **Expense Details**.
   - Used **UI Policies** to show/hide fields based on Payment Mode.

3. **Client Scripts**
   - Real-time validation to ensure **Amount** is positive.
   - Auto-fill the Date field with today’s date.

4. **Business Rules**
   - Automatically update the **Total Expense** field when a new record is added.
   - Example:
     ```javascript
     (function executeRule(current, previous /*null when async*/) {
         var gr = new GlideAggregate('u_family_expenses');
         gr.addAggregate('SUM', 'u_amount');
         gr.query();
         if (gr.next()) {
             current.u_total_expense = gr.getAggregate('SUM', 'u_amount');
         }
     })(current, previous);
     ```

5. **Reporting & Dashboards**
   - Monthly expense report.
   - Pie chart for category-wise distribution.

---

## 📜 How It Works
1. **User logs in** to the ServiceNow instance.
2. **Adds expense records** through a custom form.
3. **Business rules calculate totals** automatically.
4. **Reports and dashboards** present the expenses in visual format.

---

## 📈 Learning Outcomes
- Hands-on experience with **custom application development in ServiceNow**.
- Understanding of **client-side and server-side scripting** in ServiceNow.
- Practical usage of **reports, dashboards, and UI policies**.

---

## 🏁 Conclusion

The Calculating Family Expenses using ServiceNow project demonstrates the potential of the ServiceNow platform beyond IT Service Management by showcasing a custom-built, non-IT business application.
It highlights how ServiceNow’s low-code/no-code tools, combined with scripting capabilities, can be used to quickly develop solutions for everyday business problems such as expense tracking.

This project not only showcases my technical proficiency but also my ability to:

Understand business requirements.

Translate them into functional ServiceNow applications.

Automate processes to improve efficiency.

Present information in a user-friendly and analytical format through reports and dashboards.
