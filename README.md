![logo](https://raw.githubusercontent.com/sirvar/robin/master/assets/logo.png)
## 🚀 Android login, made simple

Almost every app has a login and signup, so why do we re-write code everytime? Let robin handle that for you.

![login](https://raw.githubusercontent.com/sirvar/robin/master/assets/login.png) ![signup](https://raw.githubusercontent.com/sirvar/robin/master/assets/signup.png)

# Usage
Add this to your **build.gradle**

```
compile 'com.sirvar:robin:0.0.1'
```

Create a new activity to handle login and signup requests that extends **RobinActivity**

```java
public class MainActivity extends RobinActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        // DO NOT call setContentView();	

        // Set title for each screen
        setLoginTitle("Sign in to Robin");
        setSignupTitle("Welcome to Robin");
        setForgotPasswordTitle("Forgot Password");		

        // Set logo for screens
        setImage(getResources().getDrawable(R.mipmap.ic_launcher));		

        // Use custom font across all views
        setFont(Typeface.createFromAsset(getAssets(), "Montserrat-Medium.ttf"));		

        // Choose theme (default is LIGHT)
        setTheme(Theme.LIGHT);
    }
}
```

## Themes
| Theme Name | Usage |
| ---------- | -----:|
| Light |  Theme.LIGHT |
| Dark | Theme.DARK &#42; |
| Flat | Theme.FLAT &#42; |
| Gradient | Theme.GRADIENT &#42; |
| Blur | Theme.BLUR &#42; |

&#42; Coming soon

## Configuration Options
| Method | Description |
| ------ | -----------:|
| `setLoginTitle(String title)` | Set the title of the login screen |
| `setSignupTitle(String title)` | Set the title of the signup screen |
| `setForgotPasswordTitle(String title)` | Set the title of the forgot password screen |
| `setTheme(Theme theme)` | Set theme from Theme enum, options above |
| `setImage(Drawable image)` | Set the Drawable image of all screens |
| `setImage(Bitmap image)` | Set the Bitmap image of all screens |
| `setFont(Typeface typeface)` | Set custom typeface to use across all screens |
| `startLoginFragment()` | Changes the visible fragment to login |
| `startSignupFragment()` | Changes the visible fragment to signup |
| `startForgotPasswordFragment()` | Changes the visible fragment to forgot password |
| `showLoginFirst()` | Shows login fragment on Activity launch |
| `showSignupFirst()` | Shows signup fragment on Activity launch |
| `enableSocialLogin()` | Displays Google and Facebook login buttons |
| `disableSocialLogin()` | Hides Google and Facebook login buttons |

## Override Methods
```java
onLogin(String email, String password)
```
```java
onSignup(String name, String email, String password)
```
```java
onForgotPassword(String email)
```
```java
onGoogleLogin()
```
```java
onFacebookLogin()
```
