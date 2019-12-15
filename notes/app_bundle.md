# APP BUNDLE

Preferred publishing format. Still upload single ver of app to Play, but instead of monolithic apk, allows Play to dynamically optimize apk user downloads, specific to their device's capabilities and settings, resulting in on avg 20% reduction in app size.

E.g., if user's locale doesn't support particular language, rscs for that language will not be included. If user adds support for that language later, Play will then deliver necessary rscs automatically.

Encourages modularization of app.

Can still publish universal apk to other app stores.
