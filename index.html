<?php

    session_start();

    $error = "";    

    if (array_key_exists("logout", $_GET)) {
        
        unset($_SESSION);
        setcookie("id", "", time() - 60*60);
        $_COOKIE["id"] = ""; 
			
		session_destroy();
        
    } else if ((array_key_exists("id", $_SESSION) AND $_SESSION['id']) OR (array_key_exists("id", $_COOKIE) AND $_COOKIE['id'])) {
        
        header("Location: loggedinpage.php"); 
        
    }
if (array_key_exists("submit", $_POST)) {
	include("connection.php");
        

        
        if (!$_POST['email']) {
            
            $error .= "An email address is required<br>";
            
        } 
        
        if (!$_POST['password']) {
            
            $error .= "A password is required<br>";
            
        } 
        
        if ($error != "") {
            
            $error = "<p>There were error(s) in your form:</p>".$error;
            
        } else {
            
            if ($_POST['signUp'] == '1') {
            
                $query = "SELECT id FROM `Secret` WHERE email = '".mysqli_real_escape_string($link, $_POST['email'])."' LIMIT 1";

                $result = mysqli_query($link, $query);

                if (mysqli_num_rows($result) > 0) {

                    $error = "That email address is taken.";

                } else {

                    $query = "INSERT INTO `Secret` (`email`, `password`) VALUES ('".mysqli_real_escape_string($link, $_POST['email'])."', '".mysqli_real_escape_string($link, $_POST['password'])."')";

                    if (!mysqli_query($link, $query)) {

                        $error = "<p>Could not sign you up - please try again later.</p>";

                    } else {

                        $query = "UPDATE `Secret` SET password = '".md5(md5(mysqli_insert_id($link)).$_POST['password'])."' WHERE id = ".mysqli_insert_id($link)." LIMIT 1";

						$id = mysqli_insert_id($link);

                        mysqli_query($link, $query);

                        $_SESSION['id'] = $id;

                        if ($_POST['stayLoggedIn'] == '1') {

                            setcookie("id", $id, time() + 60*60*24*365);

                        } 

                        header("Location: loggedinpage.php");

                    }

                } 
                
            } else {
                    
                    $query = "SELECT * FROM `Secret` WHERE email = '".mysqli_real_escape_string($link, $_POST['email'])."'";
                
                    $result = mysqli_query($link, $query);
                
                    $row = mysqli_fetch_array($result);
                
                    if (isset($row)) {
                        
                        $hashedPassword = md5(md5($row['id']).$_POST['password']);
                        
                        if ($hashedPassword == $row['password']) {
                            
                            $_SESSION['id'] = $row['id'];
                            
                            if (isset($_POST['stayLoggedIn']) AND $_POST['stayLoggedIn'] == '1') {

                                setcookie("id", $row['id'], time() + 60*60*24*365);

                            } 

                            header("Location: loggedinpage.php");
                                
                        } else {
                            
                            $error = "That email/password combination could not be found.";
                            
                        }
                        
                    } else {
                        
                        $error = "That email/password combination could not be found.";
                        
                    }
                    
                }
            
        }
        
        
}

?>

<?php include("header.php"); ?>

<div id = "homepagecontainer" class="container">

	<h1 style="color:white;">Secret Diary</h1>
	
	<p style="color:white;"><i>Store your thoughts permanently and securely!</i></p>

	<div id="error"><?php if ($error!="") {
    echo '<div class="alert alert-danger" role="alert">'.$error.'</div>';
    
} ?></div>
	
	<br>

	<form method="post" id = "signupform">
	
		<p style="color:white;"> Interested? Sign up now. </p>

		<div class="form-group">

			<input type="email"  class="form-control" name="email" placeholder="Your Email"  >
			
		</div>
		
		<div class="form-group">
			
			<input type="password" class="form-control" name="password" placeholder="Password">
		
		</div>
		
		<div class="form-check">
		
		<input type="checkbox" class="form-check-input" name = "stayLoggedIn" id="exampleCheck1" value=1>
		
		<label class="form-check-label" for="exampleCheck1" style="color:white; margin-bottom : 10px;">Stay logged in.</label>
		
		</div>
		
		<div class="form-group">
				
			<input type="hidden" class="form-control" name="signUp" value="1">
				
			<input type="submit" class="btn btn-outline-light" name="submit" value="Sign Up!">
			
		</div>

	<p><a class="toggleforms" style = "color : white;">Log in </br></a></p>
	
	</form>

	<form method="post" id = "loginform">
	
		<p style="color:white;"> Log in using your username and password!</p>

		<div class="form-group">

			<input class="form-control" type="email" name="email" placeholder="Your Email">
			
		</div>
		
		<div class="form-group">
					
			<input class="form-control" type="password" name="password" placeholder="Password">
			
		</div>
		
		<div class="form-check">
		
		<input type="checkbox" class="form-check-input" name = "stayLoggedIn" id="exampleCheck1" value=1>
		
		<label class="form-check-label" for="exampleCheck1" style="color:white;margin-bottom : 10px;">Stay logged in.</label>
		
		</div>
		
		<div class="form-group">
			
			<input class="form-control" type="hidden" name="signUp" value="0">
				
			<input class="btn btn-outline-light" type="submit" name="submit" value="Log In!">
			
		</div>
	
		<p><a class="toggleforms" style = "color : white;">Sign up </br></a></p>

	</form>
</div>
   <?php include("footer.php"); ?>