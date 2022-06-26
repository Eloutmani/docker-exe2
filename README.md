# docker-exe2
Creez un repo github nommé **docker-exe2**  
il doit etre public, avec un fichier README.md , un fichier  .gitignore valable pour le langage Python, une License MIT  
Faites un git clone dans votre directory project local   
mettre en place dans goland la connexion ssh vers votre VM   
attention a ne pas oublier le mapping sur le deployment path sur /home/ubuntu/docker-exe2  
Mettre les commandes de l'exercice suivant dans le fichier README.md

Creez un Dockerfile file dans votre projet sous Goland , qui contient  
comme image de base fabric8/tomcat-9 de tomcat 9  
copier le fichier webapp.war dans la directory  de tomcat /opt/tomcat/webapps  
faire un build d'image avec ce Dockerfile, l'image est nommée tomcat:v1  
Faire des recherches ( docker history, docker inspect) pour trouver le port utilisé par tomcat dans cette image
Faire un docker run pour creer un container a partir de l'image tomcat:v1, en background, avec le mapping de port   
20200: et le port de tomcat dans le container que vous avez trouvé  
Ouvrir votre navigateur et affiche la page d'accueil de l'application , copiez et collez le texte de cette page dans le fichier result.txt  
En utilisant portainer , allez a l'interieur du container et creer un utilisateur tomcat nommé logwire et passord: docker  
mettez cette image dans docker hub sous vtre compte docker hub  

# docker-exe2
# commandes a executer

```shell

vi Dockerfile
# put into the Docker file 
FROM fabric8/tomcat-9
ADD webapp.war /opt/tomcat/webapps

# end of Dockerfile

docker build -t tomcat:v1 .
docker images
docker history tomcat:v1
docker inspect tomcat:v1
docker run -d -p 20200:8080 --name cttomcat tomcat:v1
docker ps -a
curl http://localhost:20200
cat >result.txt
# put into the file


<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>Apache Tomcat/9.0.10</title>
        <link href="favicon.ico" rel="icon" type="image/x-icon" />
        <link href="favicon.ico" rel="shortcut icon" type="image/x-icon" />
        <link href="tomcat.css" rel="stylesheet" type="text/css" />
    </head>

    <body>
        <div id="wrapper">
            <div id="navigation" class="curved container">
                <span id="nav-home"><a href="http://tomcat.apache.org/">Home</a></span>
                <span id="nav-hosts"><a href="/docs/">Documentation</a></span>
                <span id="nav-config"><a href="/docs/config/">Configuration</a></span>
                <span id="nav-examples"><a href="/examples/">Examples</a></span>
                <span id="nav-wiki"><a href="http://wiki.apache.org/tomcat/FrontPage">Wiki</a></span>
                <span id="nav-lists"><a href="http://tomcat.apache.org/lists.html">Mailing Lists</a></span>
                <span id="nav-help"><a href="http://tomcat.apache.org/findhelp.html">Find Help</a></span>
                <br class="separator" />
            </div>
            <div id="asf-box">
                <h1>Apache Tomcat/9.0.10</h1>
            </div>
            <div id="upper" class="curved container">
                <div id="congrats" class="curved container">
                    <h2>If you're seeing this, you've successfully installed Tomcat. Congratulations!</h2>
                </div>
                <div id="notice">
                    <img src="tomcat.png" alt="[tomcat logo]" />
                    <div id="tasks">
                        <h3>Recommended Reading:</h3>
                        <h4><a href="/docs/security-howto.html">Security Considerations HOW-TO</a></h4>
                        <h4><a href="/docs/manager-howto.html">Manager Application HOW-TO</a></h4>
                        <h4><a href="/docs/cluster-howto.html">Clustering/Session Replication HOW-TO</a></h4>
                    </div>
                </div>
                <div id="actions">
                    <div class="button">
                        <a class="container shadow" href="/manager/status"><span>Server Status</span></a>
                    </div>
                    <div class="button">
                        <a class="container shadow" href="/manager/html"><span>Manager App</span></a>
                    </div>
                    <div class="button">
                        <a class="container shadow" href="/host-manager/html"><span>Host Manager</span></a>
                    </div>
                </div>
                <!--
                <br class="separator" />
                -->
                <br class="separator" />
            </div>
            <div id="middle" class="curved container">
                <h3>Developer Quick Start</h3>
                <div class="col25">
                    <div class="container">
                        <p><a href="/docs/setup.html">Tomcat Setup</a></p>
                        <p><a href="/docs/appdev/">First Web Application</a></p>
                    </div>
                </div>
                <div class="col25">
                    <div class="container">
                        <p><a href="/docs/realm-howto.html">Realms &amp; AAA</a></p>
                        <p><a href="/docs/jndi-datasource-examples-howto.html">JDBC DataSources</a></p>
                    </div>
                </div>
                <div class="col25">
                    <div class="container">
                        <p><a href="/examples/">Examples</a></p>
                    </div>
                </div>
                <div class="col25">
                    <div class="container">
                        <p><a href="http://wiki.apache.org/tomcat/Specifications">Servlet Specifications</a></p>
                        <p><a href="http://wiki.apache.org/tomcat/TomcatVersions">Tomcat Versions</a></p>
                    </div>
                </div>
                <br class="separator" />
            </div>
            <div id="lower">
                <div id="low-manage" class="">
                    <div class="curved container">
                        <h3>Managing Tomcat</h3>
                        <p>For security, access to the <a href="/manager/html">manager webapp</a> is restricted.
                        Users are defined in:</p>
                        <pre>$CATALINA_HOME/conf/tomcat-users.xml</pre>
                        <p>In Tomcat 9.0 access to the manager application is split between
                           different users. &nbsp; <a href="/docs/manager-howto.html">Read more...</a></p>
                        <br />
                        <h4><a href="/docs/RELEASE-NOTES.txt">Release Notes</a></h4>
                        <h4><a href="/docs/changelog.html">Changelog</a></h4>
                        <h4><a href="http://tomcat.apache.org/migration.html">Migration Guide</a></h4>
                        <h4><a href="http://tomcat.apache.org/security.html">Security Notices</a></h4>
                    </div>
                </div>
                <div id="low-docs" class="">
                    <div class="curved container">
                        <h3>Documentation</h3>
                        <h4><a href="/docs/">Tomcat 9.0 Documentation</a></h4>
                        <h4><a href="/docs/config/">Tomcat 9.0 Configuration</a></h4>
                        <h4><a href="http://wiki.apache.org/tomcat/FrontPage">Tomcat Wiki</a></h4>
                        <p>Find additional important configuration information in:</p>
                        <pre>$CATALINA_HOME/RUNNING.txt</pre>
                        <p>Developers may be interested in:</p>
                        <ul>
                            <li><a href="http://tomcat.apache.org/bugreport.html">Tomcat 9.0 Bug Database</a></li>
                            <li><a href="/docs/api/index.html">Tomcat 9.0 JavaDocs</a></li>
                            <li><a href="http://svn.apache.org/repos/asf/tomcat/tc9.0.x/">Tomcat 9.0 SVN Repository</a></li>
                        </ul>
                    </div>
                </div>
                <div id="low-help" class="">
                    <div class="curved container">
                        <h3>Getting Help</h3>
                        <h4><a href="http://tomcat.apache.org/faq/">FAQ</a> and <a href="http://tomcat.apache.org/lists.html">Mailing Lists</a></h4>
                        <p>The following mailing lists are available:</p>
                        <ul>
                            <li id="list-announce"><strong><a href="http://tomcat.apache.org/lists.html#tomcat-announce">tomcat-announce</a><br />
                                Important announcements, releases, security vulnerability notifications. (Low volume).</strong>
                            </li>
                            <li><a href="http://tomcat.apache.org/lists.html#tomcat-users">tomcat-users</a><br />
                                User support and discussion
                            </li>
                            <li><a href="http://tomcat.apache.org/lists.html#taglibs-user">taglibs-user</a><br />
                                User support and discussion for <a href="http://tomcat.apache.org/taglibs/">Apache Taglibs</a>
                            </li>
                            <li><a href="http://tomcat.apache.org/lists.html#tomcat-dev">tomcat-dev</a><br />
                                Development mailing list, including commit messages
                            </li>
                        </ul>
                    </div>
                </div>
                <br class="separator" />
            </div>
            <div id="footer" class="curved container">
                <div class="col20">
                    <div class="container">
                        <h4>Other Downloads</h4>
                        <ul>
                            <li><a href="http://tomcat.apache.org/download-connectors.cgi">Tomcat Connectors</a></li>
                            <li><a href="http://tomcat.apache.org/download-native.cgi">Tomcat Native</a></li>
                            <li><a href="http://tomcat.apache.org/taglibs/">Taglibs</a></li>
                            <li><a href="/docs/deployer-howto.html">Deployer</a></li>
                        </ul>
                    </div>
                </div>
                <div class="col20">
                    <div class="container">
                        <h4>Other Documentation</h4>
                        <ul>
                            <li><a href="http://tomcat.apache.org/connectors-doc/">Tomcat Connectors</a></li>
                            <li><a href="http://tomcat.apache.org/connectors-doc/">mod_jk Documentation</a></li>
                            <li><a href="http://tomcat.apache.org/native-doc/">Tomcat Native</a></li>
                            <li><a href="/docs/deployer-howto.html">Deployer</a></li>
                        </ul>
                    </div>
                </div>
                <div class="col20">
                    <div class="container">
                        <h4>Get Involved</h4>
                        <ul>
                            <li><a href="http://tomcat.apache.org/getinvolved.html">Overview</a></li>
                            <li><a href="http://tomcat.apache.org/svn.html">SVN Repositories</a></li>
                            <li><a href="http://tomcat.apache.org/lists.html">Mailing Lists</a></li>
                            <li><a href="http://wiki.apache.org/tomcat/FrontPage">Wiki</a></li>
                        </ul>
                    </div>
                </div>
                <div class="col20">
                    <div class="container">
                        <h4>Miscellaneous</h4>
                        <ul>
                            <li><a href="http://tomcat.apache.org/contact.html">Contact</a></li>
                            <li><a href="http://tomcat.apache.org/legal.html">Legal</a></li>
                            <li><a href="http://www.apache.org/foundation/sponsorship.html">Sponsorship</a></li>
                            <li><a href="http://www.apache.org/foundation/thanks.html">Thanks</a></li>
                        </ul>
                    </div>
                </div>
                <div class="col20">
                    <div class="container">
                        <h4>Apache Software Foundation</h4>
                        <ul>
                            <li><a href="http://tomcat.apache.org/whoweare.html">Who We Are</a></li>
                            <li><a href="http://tomcat.apache.org/heritage.html">Heritage</a></li>
                            <li><a href="http://www.apache.org">Apache Home</a></li>
                            <li><a href="http://tomcat.apache.org/resources.html">Resources</a></li>
                        </ul>
                    </div>
                </div>
                <br class="separator" />
            </div>
            <p class="copyright">Copyright &copy;1999-2022 Apache Software Foundation.  All Rights Reserved</p>
        </div>
    </body>

</html>
# end of file
docker exec -it cttomcat /bin/bash
# inside the container 
 useradd -m -d /opt/tomcat -U -s /bin/false logwire -p /etc/passwd docker
 docker image tag tomcat:v1 eloutmani23/tomcat
