<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>
<form method="post" action="" enctype="multipart/form-data">
<table>
      <tr> <td width="173">Foto</td>
              <td width="10">:</td>
     

        <td width="219">
                      <input type="file" name="NamaFile" />
              </td>
      </tr>
      <tr><td width="173"></td>
             <td width="10"></td>
             <td>
                    <input type="submit" name="tambah" value="Tambah"/>
                    <input type="reset" class="submitButton" value="Batal"/>
             </td>
       </tr>
</table>
</form>
<?php
if($_POST['tambah']=='Tambah')
{
//mkdir("Gambar");
$file = $_FILES['NamaFile'];
$nama_file = $file['name'];
$nama_tmp = $file['tmp_name'];
$upload_dir = "Gambar/";
move_uploaded_file($nama_tmp,$upload_dir.$nama_file);
echo "File berhasil diunggah.";
}
?>
<img width=200 height=260 src="Gambar/<?php echo $nama_file;?> ">

</body>
</html>
