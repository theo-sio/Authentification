# Authentification
test
<!DOCTYPE html>
<html>
<lang="fr">
	
	<head>
	<title>Se connecter</title>
	</head>
	
	<body>

<?php
	
	$civilite = $_POST[ 'civilite' ] ;
	$nom = $_POST['nom'];
	$prenom = $_POST[ 'prenom' ] ;
	$date_de_naissance = $_POST[ 'date_de_naissance' ] ;
	$adresse_electronique = $_POST[ 'adresse_electronique' ] ;
	$mdp = $_POST[ 'mdp' ] ;
	$adresse_postale = $_POST[ 'adresse_postale' ] ;
	$code_postale = $_POST[ 'code_postale' ] ;
	$ville = $_POST[ 'ville' ] ;
	$numero_mobile = $_POST[ 'numero_mobile' ] ;
	
	
	
	try {

		$bd = new PDO(
						'mysql:host=localhost;dbname=sbateliers' ,
						'sanayabio' ,
						'sb2021'
			) ;
		$bd->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
		
		$sql = "insert into client(civilite,nom,prenom,date_de_naissance,adresse_electronique,mot_de_passe,adresse_postale,code_postale,ville,numero_de_mobile) values('$civilite', '$nom', '$prenom', '$date_de_naissance', '$adresse_electronique', '$mdp','$adresse_postale',  $code_postale, '$ville', $numero_mobile)" ;
		$bd->exec($sql);
	    echo "New record created successfully";
	    
		} catch(PDOException $e) {
  echo $sql . "<br>" . $e->getMessage();
	}
	
		
	
?>

	</body>	
</html>
