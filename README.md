# Team-and-Player-Management-System
Overview
This project is a Team and Player Management System built using Spring Boot. It provides REST APIs to manage teams and their associated players using a one-to-many relationship. The system supports CRUD operations for both teams and players.

Functional Requirements
Folder Structure
controller: Contains the REST controller to handle API requests.

ApiController.java: Manages the REST endpoints for team and player operations.
model: Contains the entity classes for Team and Player.

Team.java: Defines the Team entity with relevant fields.
Player.java: Defines the Player entity with relevant fields.
repository: Contains the repository interfaces for data persistence.

TeamRepo.java: Provides data access operations for Team.
PlayerRepo.java: Provides data access operations for Player.
service: Contains the service class for business logic.

ApiService.java: Implements the business logic for managing teams and players.
Team Entity
The Team class has the following fields:

teamId (int): Unique identifier for the team.
teamName (String): Name of the team.
sportsName (String): Name of the sport the team is associated with.
players (List<Player>): List of players associated with the team.
Player Entity
The Player class has the following fields:

playerId (int): Unique identifier for the player.
playerName (String): Name of the player.
playerAge (int): Age of the player.
mobileNumber (long): Mobile number of the player.
team (Team): Associated team (use @JsonIgnore on getTeam() to avoid cyclic references).
Both classes include appropriate constructors, getters, and setters.

API Endpoints
POST /team: Adds a new team.

Response: Returns true if the team is successfully added, otherwise false.
POST /team/{teamId}/player: Adds a new player to the specified team.

Response: Returns true if the player is successfully added, otherwise false.
GET /team/{teamId}: Retrieves the details of a team by its ID.

Response: Returns the corresponding Team object.
GET /team: Retrieves a list of all teams, including their associated player details.

Response: Returns a List of Team objects.
GET /team/{teamId}/player/{playerId}: Retrieves the details of a specific player in a team by their ID.

Response: Returns the corresponding Player object.
GET /player: Retrieves a list of all players.

Response: Returns a List of Player objects.
Platform Guidelines
JDK Version: OpenJDK 11
Server Port: 8080
Note: Do not modify the application.properties and pom.xml files to avoid build and test case failures.

Running the Application
To run the application, navigate to the springapp directory and use the following command:
mvn spring-boot:run
