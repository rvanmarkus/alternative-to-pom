---
marp: true
---

# A alternative to Page Object Models
![bg opacity](./assets/gradient.jpg)
[image](./assets/change-my-mind.jpg)

---

# Why Page Object Models

---

```js
class LoginPage {
    navigateTo() {
        cy.visit("/login");
    }

    enterUsername(username) {
        cy.get("input[name='user']").type(username); 
    }
    enterPassword(password) {
        cy.get("[data-testid='password']").type(password); 
    }

    submit() {
        cy.get(".submit").click();
    }
}
```

---

```js
  const LoginPage = require("./LoginPage");
  
  describe("Login", () => {
    let loginPage;
  
    beforeEach(() => {
      loginPage = new LoginPage();
    });
  
    it("should allow a user to log in", () => {
      loginPage.navigateTo();
      loginPage.enterUsername("user1");
      loginPage.enterPassword("password1");
      loginPage.submit();
    });
  });
```

---

# Page Objects

1. Less brittle to changes in the UI
2. Provides a interface that's easy to program to
3. The tests resembles the way your software is used
4. It makes selectors reusable

---
