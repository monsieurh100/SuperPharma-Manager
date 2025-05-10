# 📦 Modèle UML — SuperPharma Manager
## 🧩 Entités Principales


### 🧑‍💼 `User`
idUser: int
userName: string
email : string(unique)
contact: string(unique)
password: string


### 💊 `Produit`
idProduit: int
marque: string
domaine: string
nom: string
forme: string
volume: string

### MouvStock 
idMouvstock: int 
iduser :int 
OperationStock{"Entrée","Sortie","Vente"} :string
idProduit : int
PrixUnitaire :float
Quantite : float


### 🧾 `Vente`
idVente: int
iduser :int 
dateVente: datetime
nomClient: string
identifiantFacture: string(unique)
contactClient: string
numeroClient: string

### 🧾 `DetailVente`
idDetailVente: int
iduser :int 
idVente: int
idMouvstock: int



### 📦 `Approvisionnement`
idApprovisionnement: int
iduser :int 
dateApprovisionnement: datetime
nomFournisseur: string
contactFournisseur: string

### 📦 `DetailApprovisionnement`
idDetailApprovisionnement: int
iduser :int 
idApprovisionnement: int
idMouvstock: int


### 📤 `Sortie`
idSortie: int
iduser :int 
dateSortie: datetime
motif: string


### 📤 `DetailSortie`
idDetailSortie: int
iduser :int 
idSortie: FK → Sortie
idMouvstock: FK → MouvStock


## 🔗 Relations

User -> Tables(1 à plusieurs)
Produit -> MouVStock(1 à plusieurs)
MouvStock -> Detail*(i à 1)
Vete,Approvisionnement , Sortie ->Detail* (1 à plusieurs )


