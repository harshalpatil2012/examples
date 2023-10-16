# import com.fasterxml.jackson.databind.JsonNode;
import com.fasterxml.jackson.databind.ObjectMapper;

// Retrieve the blob data from the database as a byte array
byte[] blobData = retrieveBlobDataFromDatabase(); // Replace this with your database retrieval logic

// Initialize Jackson's ObjectMapper
ObjectMapper objectMapper = new ObjectMapper();

try {
    // Deserialize the JSON data from the byte array
    JsonNode rootNode = objectMapper.readTree(blobData);

    // Extract the "customer name" and "customer ID" fields
    String customerName = rootNode.get("customer_name").asText(); // Replace "customer_name" with the actual field name
    String customerID = rootNode.get("customer_id").asText(); // Replace "customer_id" with the actual field name

    // Now you have the customer name and customer ID
    System.out.println("Customer Name: " + customerName);
    System.out.println("Customer ID: " + customerID);
} catch (Exception e) {
    e.printStackTrace();
}