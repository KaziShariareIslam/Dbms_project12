<?php
session_start();
include '../config/db.php';

if (!isset($_GET['id'])) {
    header('Location: index.php');
    exit();
}

$grade_id = $_GET['id'];

// Fetch the grade to edit
$query = "SELECT * FROM grades WHERE id = '$grade_id'";
$result = mysqli_query($conn, $query);
$grade = mysqli_fetch_assoc($result);

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $new_grade = mysqli_real_escape_string($conn, $_POST['grade']);
    
    $query = "UPDATE grades SET grade = '$new_grade' WHERE id = '$grade_id'";
    if (mysqli_query($conn, $query)) {
        header('Location: index.php');
    } else {
        echo "Error: " . mysqli_error($conn);
    }
}
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Edit Grade</title>
    <link rel="stylesheet" href="../assets/css/styles.css">
</head>
<body>
    <div class="container">
        <h1>Edit Grade</h1>
        <form action="edit.php?id=<?php echo $grade['id']; ?>" method="POST">
            <input type="text" name="grade" value="<?php echo $grade['grade']; ?>" required>
            <button type="submit" class="btn">Update Grade</button>
        </form>
    </div>
</body>
</html>
