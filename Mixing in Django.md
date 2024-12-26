### What is Mixing in Django?
  1. In Django, a mixins is a class that provides specific functionality that can be shared across multiple classes, typically used in views, to avoid code duplication and improve code reusability. A mixin is usually a small class that adds a single, focused behavior to another class, and is meant to be used with other classes to compose larger, more complex behaviors.

Mixins allow you to write cleaner, modular, and reusable code by encapsulating common functionality into small, manageable pieces.
### Why Do We Need Mixins?
  1. Code Reusability: Mixins allow you to reuse the same functionality across multiple views, reducing code duplication.
  2. Separation of Concerns: Instead of adding every piece of functionality directly into a single class (view), mixins allow you to separate concerns and keep code more organized.
  3. Modularity: Mixins help you build modular code, where you can add only the functionality you need, without affecting other parts of your code.
  4. Maintainability: Because functionality is separated into smaller, focused mixins, the code becomes easier to maintain and update.

### When to Use Mixins?
  1. You need to add the same functionality to multiple views but don’t want to repeat the same code.
  2. You want to keep views clean and focused on their specific purpose while delegating shared functionality to mixins.
  3. You are following Django’s best practices for reusing code and creating maintainable apps.
### Example of Using a Mixin in Django:
  1. A common use case for mixins in Django is the LoginRequiredMixin, which ensures that a user must be logged in to access a view.
     ```
       from django.contrib.auth.mixins import LoginRequiredMixin
       from django.contrib.auth.mixins import LoginRequiredMixin
      from django.views.generic import TemplateView
    
      class DashboardView(LoginRequiredMixin, TemplateView):
          template_name = 'dashboard.html'

     ```
In this example, LoginRequiredMixin ensures that the user must be logged in before they can access the DashboardView. This functionality is reusable and can be added to any view where login is required.

