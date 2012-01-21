s project is a working demo of using Spring Security plugins with Grails.
============================================================================

Versions
--------

 * Grails: 2.0
 * Spring Security Core: 1.2.7.1
 * Spring Security Ui: 0.2.0

Steps followed in developing this project
-----------------------------------------

1. Generate the Grails project: `grails create-app g2-ss-ui-example`
2. Install plugin from zip file `grails install-plugin lib/spring-security-ui/grails-spring-security-ui-0.2.0.zip`
3. Run the following command to install the plugins: `grails refresh-dependencies`
4. The above command generates warnings about runtime dependencies not defined within the plugin. So add the runtime dependencies for "mail", "jquery-ui" and "famfamfam" in `grails-app/conf/BuildConfig.groovy`.
5. Run the following command: `grails s2-quickstart <package-name> <name-for-user-domain-class> <name-for-role-domain-class>` and verify the entries added in `grails-app/conf/Config.groovy`. Example: `s2-quickstart me.aaron User Role`
6. Run Spring Security Ui's `s2ui-override` script for generating registration related code: `s2ui-override register me.aaron`
10. Now with the views ready, we'll look into the registration workflow. For this app, I have used the greenmail plugin as I don't want to send real messages. For this, I added a plugin dependency in `grails-app/conf/BuildConfig.groovy` and defined an SMTP port in `grails-app/conf/Config.groovy` as required by the plugin. So all emails sent (in this case for registration, forgot password) are viewable at http://localhost:8080/G2SSExample/greenmail in development.

