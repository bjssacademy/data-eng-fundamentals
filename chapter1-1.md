## Chapter 1: Introduction to Jupyter, NumPy, and pandas

### Lesson 1: Getting Started with Jupyter Notebook

**Goal of this lesson:**  
By the end of this lesson, you’ll be familiar with Jupyter Notebook, know how to navigate the interface, and write a bit of Python to test things out. We’ll keep it simple for now, just to get you comfortable.

---

#### What is Jupyter Notebook?

Jupyter Notebook is like an interactive environment for coding. You can write and run code (usually Python), add explanations, and even visualise data all in the same place. This makes it super handy for data engineers or anyone working with data. Think of it as a coding notebook where you can keep notes, code, and results all in one tidy spot.

#### Why Should You Use It?

- **Interactive coding**: You write code, run it, and see the result straight away.
- **Easy to share**: You can save everything, including your results, and share it with others.
- **Perfect for data**: Data manipulation and visualisation work beautifully in Jupyter.

---

#### Step 1: Install Jupyter Notebook

If you haven’t already got it installed, don’t worry – it’s simple.

1. Open a terminal (or command prompt on Windows).
2. Run this:

```bash
pip install notebook
```

That’s it, installation done!

---

#### Step 2: Start Jupyter Notebook

After installation, we need to run it.

1. In your terminal, just type this:

```bash
jupyter notebook
```

2. A new browser window should pop up, and you’ll see a dashboard. This is where you can create new notebooks, open existing ones, and manage your files.

If nothing happens, try opening the link it gives you in your terminal manually.

> :exclamation: As of 2020, Chrome automatically redirects all HTTP URLs to HTTPS. You can stop Chrome from automatically redirecting HTTP URLs to HTTPS for localhost by doing the following:
> 
> Go to chrome://net-internals/#hsts
>
> Enter "localhost" (without quotes) in the box underneath "delete domain security policies"
>
> Click Delete
>
> Try accessing localhost again
This only changes the setting for the localhost domain. It does not compromise security for other domains.

---

#### Step 3: Navigating the Jupyter Interface

Once your notebook is up, you’ll notice a few key parts of the interface.

- **Code Cells**: This is where the magic happens. You write your code here.
- **Markdown Cells**: You can add notes, explanations, or even headings to keep your notebook organised.
- **Run Button**: After writing your code, hit the "Run" button or press `Shift + Enter` to execute it.

---

#### Step 4: Writing Your First Code

Let’s start with something easy – we’ll write a basic bit of Python to make sure everything works.

1. Click **New** (on the right side of the dashboard) and choose **Notebook** and then **Python 3** (or whichever Python version you have installed).
2. You’ll be taken to a blank notebook.

Now, type this into your first cell:

```python
print("Hello, world!")
```

Run it by pressing `Shift + Enter` or clicking the "Run" button.

If everything’s working, you should see:

```
Hello, world!
```

Congrats – your first bit of code in Jupyter!

---

#### Step 5: Adding Explanations with Markdown

You don’t always want to write code. Sometimes, you need to explain what’s happening. That’s where Markdown comes in handy. Let’s try adding a heading.

1. Create a new cell (click on the plus sign).
2. Change it from a **Code** cell to **Markdown** (use the dropdown menu at the top).
3. Type this in the cell:

```
# This is a heading
```

4. Run the cell (again, `Shift + Enter`).

You’ll notice that the text gets formatted into a proper heading. This is great for keeping things neat and readable.

---

#### Summary

In this lesson, you’ve:
- Installed Jupyter Notebook.
- Launched it and created your first notebook.
- Run a bit of Python code to print “Hello, world!”
- Used Markdown to add some notes and headings.

Jupyter is a fantastic tool for interactive coding, and we’ll be using it throughout the course. Now that you’re all set up, we’ll soon be jumping into some data work.

Next time, we’ll get started with **NumPy**, which is one of the most important libraries for data engineering in Python.

---

If you ever get stuck or need more help with Jupyter, you can check out the official documentation [here](https://jupyter.org/documentation).


---
[>> Next Lesson](./chapter1-2.md)
