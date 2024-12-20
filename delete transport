<?php
session_start();
include '../config/db.php';

if (!isset($_GET['id'])) {
    header('Location: index.php');
    exit();
}

$transport_id = $_GET['id'];

// Delete the transport record
$query = "DELETE FROM transport WHERE id = '$transport_id'";
if (mysqli_query($conn, $query)) {
    header('Location: index.php');
} else {
    echo "Error: " . mysqli_error($conn);
}
?>
