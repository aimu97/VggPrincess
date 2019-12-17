# Récapitulatif

Master 1 Informatique 

Nom: Ayadi

Prenom:Emna

n° étudiant: 16700056

Projet: Princess Disney

## Description projet

Réseaux de neurone qui reconnaît les princesse Disney.

L'objectif est de former un réseau neuronal convolutif pour reconnaître et classer chacun de ces Princesses

Les princesses que mon réseau reconnait sont : 

	- Ariel (799 images)
	- Aurora (334 images)
	- Belle (359 images)
	- Cendrillon (303 images)
	- Jasmine (358 images)
	- Merida (349 images
	- Moana (247 images)
	- Mulan (371 images)
	- Pocahontas (403 images)
	- Raiponse (350 images)
	- Blanche-Neige (389 images)
	- Tiana (380 images)

La base de données comprend 4642 images diversifié ( figurines, jouet, dessins, images du film) en total.


## Strucuture du projet

|-------- Dataset 
			|----ariel [799 entrées]
			|----aurora [334 entrées]
			|----belle [359 entrées]
			|----jasmine [358 entrées]
			|----merida [349 entrées]
			|----moana [247 entrées]
			|----mulan [371 entrées]
			|----pocahontas [403 entrées]
			|----rapunzel [350 entrées]
			|----snowWhite [389 entrées]
			|----tiana [380 entrées]
			|----cendrella [303 entrées]
|-------- Test_exemple
|-------- Vggsmall
			|----__init__.py
			|----vggnet.py
|-------- plot.png
|-------- lb.pickle
|-------- classify.py
|-------- train.py
|-------- test epoch 50
|-------- search_bing_api.py


-Dataset: contient les 12 classes, chaque classes est son propre sous-répertoire respectif pour facilité l'analyse des étiquettes de classe

-Test_exemple: contient des images où on utilise pour tester le Cnn

-Vggsmall : contient la classe de modele vggnet

-plot.png : graphique de formation 

-lb.pickle: fichier objet "Labelbinarizer"

-princess.model : fichier modèle serialisé CNN

-train.py: script pour entraîner, serialiser le réseau CNN et etiqueter le binariseur sur le disque.

- classsify.py : script de test

-test epoch 50: fichier qui contient les resulat obtenu avec 50 epochs

-search_bing_api.py: api qui a permis de alimenter le dataset( clef microsoft : essaie de 7 jours gratuit) 

## Sources


 Etape 1 API pour le dataset:
 - Api microsoft, essaie 7 jours : 
 -https://docs.microsoft.com/en-us/azure/cognitive-services/bing-image-search/quickstarts/python

 -https://docs.microsoft.com/en-us/azure/cognitive-services/Bing-Web-Search/paging-search-results

 -https://pmcg2k15.wordpress.com/category/pyimagesearch/
        
        
 Vgg16:
  - https://www.pyimagesearch.com/wp-content/uploads/2018/04/cnn_keras_smallervggnet.png

  - https://machinelearningmastery.com/use-pre-trained-vgg-model-classify-objects-photographs/
  
  - https://engmrk.com/vgg16-implementation-using-keras/

  - https://keras.io/layers/pooling/
  -https://keras.io/applications/#vgg16

 Model/Base (suivie etape par etape):
  - https://www.pyimagesearch.com/2017/12/11/image-classification-with-keras-and-deep-learning/

  -https://pmcg2k15.wordpress.com/category/pyimagesearch/

  -https://stackabuse.com/image-recognition-in-python-with-tensorflow-and-keras/
  -https://blog.keras.io/building-powerful-image-classification-models-using-very-little-data.html

 
 ## Usage
 

 ``` python3 train.py --dataset dataset --model princess.model --labelbin lb.pickle```

 Création du model de training. Pour 100 epcohs cela prend 2h30 - 3h reconnais toutes les princesses

 Pour 50 epochs cela prend 1h30-2h et ne reconnais pas toute les princesses tel que Aurora



 ```python classify.py --model princess.model --labelbin lb.pickle \ --image test_exemple/moana.png```

 un exemple pour tester si le reseau reconnais la princesse et si c'est la bonne étiquette