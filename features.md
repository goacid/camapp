# Elli-Food — Catalogue des fonctionnalités

Elli-Food vise à simplifier la gestion des repas pour les adultes avec un TDAH : savoir ce qui est disponible, choisir quoi manger, anticiper les courses et réduire la charge mentale.

L'application actuelle porte le nom **Repas du jour**. C'est une application web statique, utilisable sur mobile et ordinateur, dont l'interface et la logique sont regroupées dans [index.html](./index.html). Les données sont principalement conservées dans le navigateur, comme indiqué dans le [README](./README.md).

Ce catalogue rassemble l'existant, les demandes Elli-Food et des propositions complémentaires. Il ne constitue pas un engagement à tout développer.

## Comment lire les tableaux

| Statut | Signification |
|---|---|
| ✅ Implémenté | Fonction présente dans le code et accessible dans l'interface actuelle. |
| 🟡 Partiel | Une base existe, mais le parcours est incomplet, non accessible ou dépend d'un environnement particulier. |
| ⬜ À proposer | Fonctionnalité à développer ; aucune implémentation identifiée dans le projet actuel. |

Les statuts résultent d'une lecture du code, **pas d'une validation complète en navigateur**. Une coche verte ne signifie donc pas absence de bugs.

**Priorités suggérées :** **Haute** pour les fondations et les usages essentiels ; **Moyenne** pour les enrichissements ; **Exploration** pour les pistes ambitieuses à expérimenter. **—** indique une fonctionnalité déjà présente. Ces priorités restent ajustables.

## 1. Accueil et aide à la décision

Base observée : [écran Aujourd'hui et suggestions](./index.html#L814).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Voir les repas d'aujourd'hui et de demain | ✅ Implémenté | L'accueil affiche les recettes planifiées, le créneau et le nombre de personnes. | — |
| Voir les aliments à utiliser rapidement | ✅ Implémenté | Liste des ingrédients dont la date limite est dans trois jours ou moins, y compris les dates dépassées. Les plats prêts sont exclus de ce bloc. | — |
| Obtenir trois suggestions selon le stock | ✅ Implémenté | Trois recettes du catalogue sont mises en avant selon le pourcentage d'ingrédients disponibles en quantité suffisante ; ce n'est pas une génération de nouvelles recettes. | — |
| SOS « On mange quoi là tout de suite ? » | ⬜ À proposer | Une action directe proposant un repas réalisable avec le stock, puis permettant de changer de proposition, jusqu'à cinq alternatives. Expliquer le manque de choix plutôt que proposer des recettes irréalisables. | Haute |
| Mode « faible énergie » | ⬜ À proposer | Privilégier les repas très simples, les plats prêts, peu d'étapes et peu de vaisselle, avec un choix limité pour éviter la surcharge. | Haute |
| Comprendre pourquoi une recette est proposée | ⬜ À proposer | Afficher des raisons courtes : « tout en stock », « 10 minutes », « utilise les courgettes à consommer bientôt ». | Moyenne |
| Générer une nouvelle recette à partir du stock | ⬜ À proposer | Aller au-delà du catalogue existant, avec ingrédients et quantités vérifiables. Si une IA est utilisée, prévoir une validation humaine et le respect des exclusions alimentaires. | Exploration |

## 2. Stock et saisie des aliments

Bases observées : [unités](./index.html#L275), [regroupement](./index.html#L322), [formulaires](./index.html#L382), [affichage du stock](./index.html#L434), [actions groupées](./index.html#L477), [consommation](./index.html#L508).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Ajouter, modifier et supprimer un aliment | ✅ Implémenté | Nom, quantité, unité, rangement, date d'ajout, date limite facultative, caractère périssable et icône. | — |
| Organiser le stock par rangement | ✅ Implémenté | Frigo, congélateur, placard et garage prédéfinis ; affichage par rangement ou en liste, avec tableau éditable sur grand écran. | — |
| Gérer les unités et conversions compatibles | ✅ Implémenté | Conversions de poids et de volumes, unités de comptage et ajout d'unités personnalisées. Pas de conversion automatique d'une pièce en grammes. | — |
| Regrouper les doublons compatibles | ✅ Implémenté | Fusion par nom normalisé, rangement, type ingrédient/plat prêt et famille d'unité ; conservation de la date limite la plus proche. | — |
| Consommer une partie d'un produit | ✅ Implémenté | Prévisualisation du reste et retrait du produit lorsque sa quantité est épuisée. | — |
| Modifier plusieurs articles à la fois | ✅ Implémenté | Déplacement, suppression et changement du caractère périssable sur une sélection. | — |
| Identifier les plats prêts | ✅ Implémenté | Marquage et présentation distincts des ingrédients ; ils ne sont pas comptés comme ingrédients des recettes. | — |
| Attribuer une icône au produit | ✅ Implémenté | Suggestion selon son nom et remplacement manuel possible. | — |
| Rechercher et filtrer le stock | ⬜ À proposer | Recherche par nom, filtres par rangement, date limite, plats prêts ou informations manquantes. | Haute |
| Personnaliser les rangements | ⬜ À proposer | Ajouter, renommer et réordonner les lieux de stockage. | Moyenne |
| Conserver des lots distincts d'un même produit | ⬜ À proposer | Ne pas fusionner des achats ayant des dates limites différentes ; distinguer les quantités de chaque lot. | Haute |
| Signaler les données à compléter | ⬜ À proposer | Badge et liste de vérification pour les dates inconnues, quantités incertaines ou rangements non confirmés, notamment après import. Aujourd'hui, nom et quantité sont obligatoires à l'ajout manuel, mais la date limite ne l'est pas. | Haute |
| Importer un ticket de caisse ou une facture | ⬜ À proposer | Extraire les produits et quantités depuis une image ou un document, puis faire confirmer la correspondance des produits, les unités et les doublons avant ajout. Les dates limites ne doivent pas être inventées. | Exploration |
| Ajouter du stock par dictée orale | ⬜ À proposer | Interpréter une phrase comme « deux briques de lait dans le placard », avec récapitulatif modifiable avant validation. | Exploration |
| Ajouter du stock depuis une photo | ⬜ À proposer | Reconnaître des produits ou étiquettes, signaler les incertitudes et demander confirmation ; une photo ne garantit pas la quantité ni la date limite. | Exploration |
| Scanner un code-barres | ⬜ À proposer | Préremplir le nom et le conditionnement ; demander séparément la quantité en stock et la date limite. | Moyenne |

## 3. Dates limites et anti-gaspillage

Bases observées : [calcul de disponibilité et produits périmés](./index.html#L356), [indicateurs de date](./index.html#L418), [détail de recette](./index.html#L730).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Distinguer visuellement les dates proches ou dépassées | ✅ Implémenté | Libellés dans le stock, mise en évidence des dates dépassées et récapitulatif à l'accueil. Ce sont des indications dans l'application, pas des notifications. | — |
| Avertir lorsqu'une recette utilise un produit à date dépassée | ✅ Implémenté | Le détail indique « Produit périmé à vérifier ». Le stock concerné reste toutefois compté dans la disponibilité. | — |
| Consommer d'abord les dates les plus proches lors d'une cuisson | ✅ Implémenté | La déduction des quantités parcourt les articles correspondants par date limite croissante. | — |
| Classer les suggestions selon l'urgence des dates | 🟡 Partiel | Dates et alertes existent, mais le classement actuel repose uniquement sur la disponibilité des ingrédients. Ajouter un score anti-gaspillage pour les produits encore utilisables. | Haute |
| Distinguer DLC et DDM | ⬜ À proposer | Enregistrer le type de date. Exclure des suggestions les aliments à DLC dépassée ; une DDM dépassée appelle une vérification adaptée au produit et à sa conservation, pas une autorisation automatique de consommation. | Haute |
| Rappeler les échéances sans surcharger | ⬜ À proposer | Rappels facultatifs, regroupés et configurables ; inclure les plats prêts et prévoir un report simple. | Moyenne |
| Suivre ouverture, congélation et décongélation | ⬜ À proposer | Dates et consignes de conservation distinctes ; ne pas assimiler congélation et remise à zéro automatique de la durée de conservation. | Moyenne |
| Mesurer le gaspillage évité ou constaté | ⬜ À proposer | Distinguer consommé et jeté, puis présenter un bilan simple et non culpabilisant. | Exploration |

## 4. Recettes et personnalisation des suggestions

Bases observées : [catalogue initial](./index.html#L240), [création et édition](./index.html#L541), [cuisson](./index.html#L666).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Disposer d'un catalogue de départ | ✅ Implémenté | Recettes préchargées avec ingrédients, durée et indication de congélation. | — |
| Créer, modifier et supprimer des recettes | ✅ Implémenté | Saisie du nom, de la durée, du nombre de portions, des ingrédients et du caractère congelable. | — |
| Adapter les quantités au nombre de personnes | ✅ Implémenté | Ajustement des portions et recalcul des quantités dans le détail et lors de la cuisson. | — |
| Voir la faisabilité selon le stock | ✅ Implémenté | Pourcentage d'ingrédients disponibles en quantité suffisante, indicateur coloré et liste des manquants ; tri par disponibilité. | — |
| Confirmer les quantités réellement cuisinées | ✅ Implémenté | Le bouton « Cuisiné » ouvre une confirmation ajustable avant déduction du stock. Il ne crée pas d'historique de cuisson. | — |
| Ajouter les étapes de préparation | ⬜ À proposer | Instructions structurées dans chaque recette, absentes du modèle actuel. | Haute |
| Filtrer par typologie | ⬜ À proposer | Végétarien, froid, soupe, tarte, été, hiver, spécial enfants ; permettre plusieurs catégories par recette. | Haute |
| Rechercher et filtrer par contraintes pratiques | ⬜ À proposer | Nom, durée maximale, matériel disponible, nombre d'ingrédients et niveau d'effort. | Haute |
| Noter une recette de zéro à cinq étoiles | ⬜ À proposer | Distinguer la note zéro d'une recette non notée, et permettre de modifier sa note. | Moyenne |
| Trier les recettes par note | ⬜ À proposer | Compléter le tri actuel par disponibilité avec un tri explicite sur les notes. | Moyenne |
| Archiver une recette sans la supprimer | ⬜ À proposer | Masquer des suggestions et permettre la restauration depuis une liste d'archives. | Moyenne |
| Conserver l'historique des recettes cuisinées | ⬜ À proposer | Date, portions et retour rapide ; ne pas déduire un historique du seul bouton « Cuisiné ». | Haute |
| Apprendre les préférences au fil des semaines | ⬜ À proposer | Utiliser notes, choix et cuissons confirmées, avec accord de l'utilisateur. L'écoulement d'un stock ne prouve pas à lui seul qu'un aliment a été apprécié. | Exploration |
| Séparer « Recettes habituelles » et « Pour changer un peu » | ⬜ À proposer | Conserver des choix rassurants tout en proposant une diversité contrôlée ; éviter les répétitions sans ignorer les exclusions alimentaires. | Moyenne |
| Choisir la fréquence de renouvellement des suggestions | ⬜ À proposer | Réglage de fréquence et bouton de renouvellement manuel ; conserver les choix en cours et recalculer la faisabilité si le stock change. | Moyenne |
| Importer une recette depuis une URL ou un document | ⬜ À proposer | Préremplissage à vérifier, avec conservation du lien source et respect des droits de réutilisation. | Exploration |
| Proposer des substitutions d'ingrédients | ⬜ À proposer | Alternatives selon le stock et les préférences, avec confirmation des quantités et sans garantie implicite pour les allergies. | Exploration |

## 5. Préférences alimentaires et foyer

Bases observées : [détection des refus](./index.html#L362), [formulaire de membre](./index.html#L645), [rendu familial](./index.html#L778).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Enregistrer les membres et leurs ingrédients refusés | 🟡 Partiel | Modèle et fonctions d'ajout/suppression présents, mais aucun onglet ni parcours visible ne permet d'administrer les membres. | Haute |
| Signaler une incompatibilité alimentaire | 🟡 Partiel | Des avertissements peuvent apparaître dans les recettes et le planning si des membres sont déjà enregistrés. La configuration n'est pas accessible et les suggestions ne sont pas filtrées. | Haute |
| Disposer d'un onglet « Préférences alimentaires » | ⬜ À proposer | Écran dédié aux ingrédients exclus, goûts et régimes, pour soi ou pour chaque membre du foyer. | Haute |
| Activer ou désactiver les préférences en un bouton | ⬜ À proposer | Interrupteur explicite pour les préférences de goût. Garder les allergies séparées pour éviter leur désactivation involontaire. | Haute |
| Exclure réellement les ingrédients non souhaités des suggestions | ⬜ À proposer | Appliquer les préférences au SOS, aux suggestions et à la planification assistée, plutôt que seulement afficher un avertissement. | Haute |
| Distinguer goûts, régimes et allergies | ⬜ À proposer | Contraintes séparées et visibles ; les correspondances textuelles actuelles ne constituent pas une détection fiable des allergènes. | Haute |
| Adapter les recettes aux convives du repas | ⬜ À proposer | Choisir les participants et leurs contraintes plutôt qu'appliquer les refus de tout le foyer à chaque repas. | Moyenne |

## 6. Planning des repas

Bases observées : [planifier une recette](./index.html#L566), [ajout au planning](./index.html#L617), [liste des repas](./index.html#L756).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Planifier une recette à une date | ✅ Implémenté | Depuis une recette ou l'onglet Semaine, avec nombre de personnes et créneaux « Midi (moi) » ou « Soir (famille) ». | — |
| Consulter et retirer les repas prévus | ✅ Implémenté | Liste chronologique ; consultation des repas déjà prévus pour une date dans le formulaire d'une recette. L'onglet Semaine n'est pas une grille de calendrier. | — |
| Déplacer ou modifier un repas prévu | ⬜ À proposer | Changer date, créneau ou portions sans supprimer puis recréer l'entrée. | Haute |
| Personnaliser les créneaux de repas | ⬜ À proposer | Petit-déjeuner, déjeuner, dîner, collation ou autre, sans dépendre des deux créneaux actuels. | Moyenne |
| Générer un planning assisté | ⬜ À proposer | Proposer quelques jours selon stock, dates, temps, convives et variété, avec validation repas par repas. | Exploration |
| Prévoir les restes et la cuisine en avance | ⬜ À proposer | Lier les portions préparées à de futurs repas et créer des plats prêts en stock après confirmation de cuisson. | Moyenne |
| Réserver le stock pour les repas planifiés | ⬜ À proposer | Signaler lorsqu'un ingrédient est engagé dans plusieurs repas et distinguer stock total et stock disponible hors planning. | Haute |

## 7. Courses

Bases observées : [calcul des besoins](./index.html#L368), [ajouts manuels](./index.html#L631), [liste par rayon](./index.html#L768), [enregistrement d'un achat](./index.html#L863).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Calculer les courses depuis le planning | ✅ Implémenté | Somme des besoins des repas enregistrés, ajustée aux portions, moins le stock compatible. Le calcul porte sur tout le planning enregistré, sans sélection de période. | — |
| Ajouter un article manuellement à la liste | ✅ Implémenté | Nom, quantité et unité, indépendamment des recettes. | — |
| Regrouper les achats par rayon | ✅ Implémenté | Classement automatique par règles sur les noms, avec catégorie « Autres ». | — |
| Transférer un achat dans le stock | ✅ Implémenté | Le bouton « Acheté » ajoute la quantité au placard, sans date limite ; le rangement et la date peuvent ensuite être modifiés dans le stock. | — |
| Choisir la période des courses | ⬜ À proposer | Cette semaine, prochains jours ou intervalle personnalisé, sans reprendre les anciens repas. | Haute |
| Confirmer les détails d'un achat | ⬜ À proposer | Quantité réellement achetée, conditionnement, rangement et date limite avant entrée en stock. | Haute |
| Cocher, modifier et retirer les articles manuels | ⬜ À proposer | Distinguer « pris en rayon », « acheté » et « retiré de la liste », sans modifier prématurément le stock. | Moyenne |
| Partager ou exporter la liste | ⬜ À proposer | Version imprimable ou partage textuel simple ; collaboration en direct à traiter avec la synchronisation du foyer. | Moyenne |
| Suivre un budget prévisionnel | ⬜ À proposer | Prix facultatifs et estimation clairement distinguée du total réel, éventuellement alimentés par les tickets validés. | Exploration |

## 8. Accompagnement TDAH et accessibilité

Bases observées : [interface adaptative et styles](./index.html#L5), [annulation temporaire](./index.html#L465).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Utiliser une interface mobile et ordinateur | ✅ Implémenté | Navigation par onglets, vues adaptées à la largeur et fenêtres de saisie. | — |
| Bénéficier du thème sombre du système | ✅ Implémenté | Adaptation CSS à la préférence système ; pas de sélecteur manuel clair/sombre dans les réglages. | — |
| Annuler certaines actions récentes | ✅ Implémenté | Message temporaire avec bouton d'annulation pour certaines suppressions et la validation d'une cuisson ; pas d'historique général des actions. | — |
| Mode simplifié et nombre de choix réduit | ⬜ À proposer | Masquer les fonctions secondaires et afficher une prochaine action claire, sans supprimer les données. | Haute |
| Guider la cuisine étape par étape | ⬜ À proposer | Une étape à la fois, progression visible et reprise au bon endroit, après ajout des instructions de préparation. | Moyenne |
| Utiliser des minuteurs de cuisson | ⬜ À proposer | Plusieurs minuteurs nommés liés aux étapes, sans confondre temps écoulé et confirmation de cuisson. | Moyenne |
| Choisir des rappels bienveillants | ⬜ À proposer | Rappels facultatifs de repas ou de préparation, avec horaires calmes, report et désactivation faciles. | Moyenne |
| Conserver une saisie interrompue | ⬜ À proposer | Brouillon récupérable après fermeture involontaire ou changement d'écran. | Haute |
| Renforcer et vérifier l'accessibilité | 🟡 Partiel | Labels, indicateurs de focus et certains attributs ARIA existent ; navigation clavier, gestion du focus des fenêtres, contrastes et lecteurs d'écran restent à vérifier et compléter. | Haute |
| Réduire les effets visuels | ⬜ À proposer | Option de contraste renforcé et réduction des effets de transparence ou d'animation pour améliorer le confort. | Moyenne |

## 9. Données, sauvegarde et partage

Bases observées : [chargement local](./index.html#L259), [sauvegarde et connexion conditionnelle](./index.html#L870), [limites documentées](./README.md).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Retrouver ses données sur le même navigateur | ✅ Implémenté | Sauvegarde via localStorage du stock, des recettes, du planning et des réglages. Effacer les données du navigateur les supprime ; les erreurs de sauvegarde ne sont pas signalées explicitement. | — |
| Synchroniser ses données avec un compte | 🟡 Partiel | Une connexion via `claude.use('db')` et `claude.use('user')` est prévue si cet environnement existe. Ce n'est pas une authentification ni une synchronisation autonome disponible sur le site standard. | Haute |
| Exporter et restaurer une sauvegarde | ⬜ À proposer | Fichier contenant les données, contrôle de validité à l'import et confirmation avant remplacement ou fusion. | Haute |
| Signaler clairement l'état d'enregistrement | ⬜ À proposer | Distinguer enregistré localement, synchronisé, en attente et échec ; alerter sur les données non sauvegardées. | Haute |
| Partager le stock et le planning d'un foyer | ⬜ À proposer | Comptes, invitations et droits d'accès, avec gestion des modifications concurrentes pour éviter les écrasements. | Exploration |
| Installer l'application et l'ouvrir hors connexion | ⬜ À proposer | Version PWA avec mise en cache explicite de l'application. La persistance locale actuelle ne garantit pas son ouverture sans réseau. | Moyenne |
| Contrôler ses données et les traitements externes | ⬜ À proposer | Export, suppression volontaire, permissions photo/micro et information claire avant tout envoi de tickets, photos ou préférences à un service externe. | Haute |

## 10. Réglages

Base observée : [personnalisation de la couleur](./index.html#L848).

| Fonctionnalité | Statut | Existant / limites ou proposition | Priorité suggérée |
|---|---|---|---|
| Choisir la couleur principale | ✅ Implémenté | Sept couleurs proposées, conservées dans les données locales. | — |
| Configurer les portions habituelles du foyer | ⬜ À proposer | Valeurs par défaut personnelles pour les repas, plutôt que les nombres prédéfinis actuels. | Moyenne |
| Régler le seuil des alertes de date | ⬜ À proposer | Remplacer le seuil fixe de trois jours par un réglage compréhensible, sans masquer les dates dépassées. | Moyenne |
| Centraliser fréquence des suggestions et rappels | ⬜ À proposer | Réunir les réglages des fonctions décrites plus haut, avec activation volontaire des notifications. | Moyenne |
| Choisir explicitement le thème | ⬜ À proposer | Clair, sombre ou système, indépendamment de la couleur principale. | Moyenne |

## Ordre de développement conseillé

1. **Fiabiliser les fondations** : sauvegarde exportable, état d'enregistrement visible, données incomplètes, lots distincts et distinction DLC/DDM.
2. **Réduire la charge mentale au quotidien** : SOS, mode faible énergie, recherche, préférences accessibles et suggestions anti-gaspillage.
3. **Faciliter la préparation** : étapes de recettes, historique, notes, modification du planning, période des courses et confirmation des achats.
4. **Personnaliser sans enfermer dans la routine** : recettes habituelles et découvertes, fréquence de renouvellement, rappels choisis.
5. **Expérimenter les fonctions avancées** : import ticket/photo/dictée, apprentissage des goûts, génération et collaboration du foyer.

Les fonctions d'import et d'apprentissage gagneront à s'appuyer sur un stock fiable, des confirmations simples et des préférences explicites. Une suggestion doit rester une aide à la décision, jamais une garantie de sécurité alimentaire.
