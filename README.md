SYMFONY 2.8 BLOG COURRIAN YANNICK
=================================

Blog réalisé grâce au bundle EDBLOGBUNDLE https://github.com/EtonDigital/EDBlogBundle

Installation:
============

1) Clôner le repository
2) Importer le fichier de la base de donnée "symfony.sql" dans votre gestionnaire de base de données

Ensuite dans le dossier blog-master:
----------------------------------
1) composer install.
2) Nous allons maintenant corriger deux erreurs qui sont dans le vendor.
2) blog-master\vendor\ed\blog-bundle\Security\Authorization\Voter\ArticleVoter.php LIGNE 48


        }
        catch(\Exception $e)
        {
            return false;
        }
to


        catch(\Exception $e)
        {
            return false;
        }
        catch(\Error $e)
        {
            return false;
        }


3) blog-master\vendor\ed\blog-bundle\Resources\views\Comment\comment.html.twig LIGNE 3
    * {{ comment.id|encrypt }}
   
to
   
    * {{ comment.id }}

4) lancer le serveur : php app/console server:run
5) utilisateur pseudo : admin   mdp: admin