# Host Configuration

When you set up your web host be sure to point the web root to `public` directory. Just as you would a normal Laravel installation.

**Alternate Directories for cPanel or Virtualmin**

In some environments like cPanel or Virtualmin, it may be difficult to use the `public` directory as the web root. In these cases we suggest symlinking the `public` directory to `public_html`:

```
ln -s public public_html
```

You may also simply rename the `public` directory to `public_html`. Path hints will automatically use the correct path.
