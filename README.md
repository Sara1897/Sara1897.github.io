# Sara1897.github.io
Nous avons réalisé une carte en ligne, présentant une orthophotographie d’une résolution de 3.14 cm sur l’aéroport de Paris-le-Bourget. En complément, vous retrouverez un descriptif qui explique la méthode utilisée afin d’héberger les tuiles de l’orthophotographie. 

1) La création de tuile 

Il a plusieurs manières de créer des tuiles à l’aide de QGIS. La plus facile, consiste à utiliser GDAL Tiles. Cet outil permet de créer un dossier contenant les tuiles, donc plusieurs images au format PNG dans une multitude de sous-dossier. Ces images devront être hébergés sur un serveur afin de pouvoir extraire le lien de ce serveur et l’intégrer à notre carte en ligne.

Le site internet Maptiler est une plate-forme logicielle pour la création de cartes numériques. Elle propose la création de tuile et l’hébergement de tuile au format PNG enregistré dans un Géopackage. Mais elle propose aussi l’hébergement de tuile au format MB tile qui sont un format spécifique de tuile adapté au serveur de Maptiler. Etant donné la simplicité du process, nous avons décidé de créer des tuiles mbtile avec le logiciel QGIS. 

Les tuiles vont du zoom 12 à 20. Etant donné que nous avons une orthophotographie, le zoom a privilégié ne commence par par une vue « globe » mais par un zoom déjà prononcé de l’orthophographie. En effet, ce qui nous intéresse, c’est d’avoir la possibilité de zoomer au plus loin que ce nous propose l’orthophotographie en vision nette. Ensuite, nous avons pris une taille de tuile de 20 : cela permet de rendre le traitement moins long et le fichier moins lourd. 

La taille du fichier MBTiles est de 479 624 Ko. Nous l’avons intégré à notre cloud. Il n’est possible d’héberger qu’un fichier de tuile sur le cloud de Maptiler avec la version gratuite. Maptiler fournit le lien pour ajouter les tuiles sur une carte Leaflet. Nous avons donc suivit le schéma classique d’ajout d’une tuile sur un script Leaflet, de cette façon : L.tileLayer('https://api.maptiler.com/tiles/3b88fd18-b707-41fa-a09b-614877ca1335/{z}/{x}/{y}.png?key=nuHM9zBF51hpgnx2PHDG',{
        attribution: null,
        crossOrigin: true
      }).addTo(map);

Nous avons ensuite ajouté un point de contrôle de la tuile afin de la sélectionner de la désélectionner comme bon nous semble. 

2) La création d’un projet Github
3
Un site web GitHub se fait en créant un nouveau projet GitHub. Ce projet va contenir un ensemble de dossier, dont un contenant le lien html. 
Le nom du projet sera notre nom d’utilisateur, c’est-à-dire Sara1897.github.io. Cela indique à Github que nous avons créez un projet spécial de page Web. Il saura alors qu'il faut transférer nos fichiers sur cette URL. 

Nous mettons comme description celle-ci : 
« Nous avons réalisé une carte en ligne, présentant une orthophotographie d’une résolution de 3.14 cm sur l’aéroport de Paris-le-Bourget. En complément, vous retrouverez un descriptif qui explique la méthode utilisée afin d’héberger les tuiles de l’orthophotographie ». 
Nous avons créé un lien html sur Github juste en remplaçant l’onglet README.md par site_web.html et nous y avons copié coller le script de la carte en ligne crée. 
De ce fait, à l’adresse Sara1897.github.io, il est possible d’accéder à la carte en ligne. 
De plus, nous rajoutons ce descriptif, dans l’onglet READ.ME.
