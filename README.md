# Gewinn-und-Verlust

<html>
	<head>
		<title>Tabelle bauen</title>
			
		<meta charset="utf-8">
    </head>
		<script>
			"use strict";
			function programm() {
		
                var vAusgabe;
                var vKostenVar;
                var vKostenFix;
                var vProduktion;
                var vStück;
                var vKosten;
                var vErlös;
                var vGewinn;
                var vBemerkung;
                var vStart=1000;
                var vBEP;
                var vSchwelle;

                vProduktion= parseFloat(document.getElementById("idProduktion").value);
                vKostenFix= parseFloat(document.getElementById("idKostenFix").value);
                vKostenVar= parseFloat(document.getElementById("idKostenVar").value);
                vStück= parseFloat(document.getElementById("idStück").value);

                vAusgabe = "";
			vAusgabe = vAusgabe + "<table border=1>";
			vAusgabe = vAusgabe + "<tr><th>Menge</th><th>Kosten K(x)</th><th>Erlös E(x)</th><th>Gewinn G(x)</th><th>Bemerkung</th></tr>";
              
               while (vStart<=vProduktion) {
				
				vKosten = vKostenFix + vKostenVar * vStart;
				vErlös= vStück * vStart;	
                vGewinn= vErlös - vKosten;	
				
				if(vGewinn<0){

                    vBemerkung="Verlustzone"
                    
				
				vAusgabe = vAusgabe + "<tr><td>" + vStart + "</td><td>" + vKosten + "</td><td>" + vErlös + "</td><td style= color:red>" + vGewinn + "</td><td>" + "Nya nya ^.^ du verlierst kohle" + "</td></tr>";


				}
				
				else {
                
                 vAusgabe = vAusgabe + "<tr><td>" + vStart + "</td><td>" + vKosten + "</td><td>" + vErlös + "</td><td>" + vGewinn + "</td><td>" + "Das gibt moneten" + "</td></tr>";
}
			     vStart=vStart + 1000;

		

}
                vAusgabe = vAusgabe + "</table>";

                vBEP = vKostenFix / (vStück - vKostenVar);
                vSchwelle = vBEP * vStück;

                vAusgabe=vAusgabe + "Break-Even-Point:  " + vBEP + " Stück<br>";
                vAusgabe=vAusgabe + "Gewinnschwelle:  " + vSchwelle + "€";

                document.getElementById("idAusgabe").innerHTML= vAusgabe;
            }
            
        

              


		</script>
	<body>

        <h1>Gewinn- und Erlösung </h1>
	
		  Kosten Variable(k) <br><input id="idKostenVar" type="text" value="4.50"></br>
          Kosten Fix <br><input id="idKostenFix" type="text" value="12800"> <br>
	      Produktionsmengen(X) <br><input id="idProduktion" type="text" value="20000"><br>
          Stückpreise(p) <br><input id="idStück" type="text" value="6"><br><br>
		
		<button onClick="programm();">Wertetabelle erzeugen!</button><br/><br/>
        <div id="idAusgabe">Button klicken!</div>



        <h1>Die Katze Freut sich das du jetzt rechnen kannst \(^.^)/</h1>
		
	</body>
</html>
