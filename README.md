Gléria pre Pulse3

Upravil som pôvodnú gallery.php a nazval som tento skript gallery-opti.php.

V tejto upravenej verzii môžete (nemusíte)zadať 3 parametre: 

šírka obrázku (imgwidth), predvolená šírka je 120px. 
výška obrázku (imgheight), predvolená výšk je 100px. 
číslo obrázku (imgnum), predvolená hodnota je 0, (0 = všetky obrázky) ; (2 = druhý obrázok) ; (if 10 = no exist) then imgnum = 0 (all image) 


Examples 1: imgwidth = "120", imgheight = "100", imgnum = "0" .
<code>
<?php $imgwidth = "120"; $imgheight = "100"; $imgnum = "0"; $gallery ="Gallery1"; include($_SERVER["DOCUMENT_ROOT"]."pulsepro/includes/gallery-opti.php"); ?> 
</code 
Examples 2: imgwidth = "180", imgheight = "120", imgnum = "0" .
<code>
<?php $imgwidth = "180"; $imgheight = "120"; $imgnum = "0"; $gallery ="Gallery1"; include($_SERVER["DOCUMENT_ROOT"]."pulsepro/includes/gallery-opti.php"); ?> 
 </code>
Examples 3: imgwidth = "200", imgheight = "150", imgnum = "2" .
<code>
<?php $imgwidth = "200"; $imgheight = "150"; $imgnum = "2"; $gallery ="Gallery1"; include($_SERVER["DOCUMENT_ROOT"]."pulsepro/includes/gallery-opti.php"); ?> 
</code> 
Examples 4: imgwidth = "200", imgheight = "150", imgnum = "10" . ??? imgnum = "10" = no exist (picture does not exist). 
<code>
<?php $imgwidth = "200"; $imgheight = "150"; $imgnum = "6"; $gallery ="Gallery1"; include($_SERVER["DOCUMENT_ROOT"]."pulsepro/includes/gallery-opti.php"); ?>
</code>

----------------------------------
Do skriptu "manage-photo.php" som pridal čast kódu:

		<p><b>Optional Thumbnail Gallery</b></p>
		<input value = '&lt;?php $imgwidth = "120"; $imgheight = "100"; $imgnum = "0"; $gallery ="<?php if (!empty($_GET["g"])) { echo htmlentities($_GET["g"]);} ?>"; include($_SERVER["DOCUMENT_ROOT"]."/<?php echo $pulse_dir; ?>/includes/<?php echo 'gallery-opti.php'; ?>"); ?&gt;' onClick = "select_all(this)"> 
