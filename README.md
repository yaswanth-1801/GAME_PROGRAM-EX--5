# GAME_PROGRAM-EX--5

# Aim
To implement a gameplay feature where the player collects ammo pickups in the game world. Upon collecting ammo, the player's ammo count increases, enabling more bullet spawns (shots).

# Procedure
1. Setup Player Character
     * Open your PlayerCharacter Blueprint.s
     * Add a new Integer variable named AmmoCount.
     * Set an initial default value (e.g., AmmoCount = 10).
     * Ensure you have a shooting mechanism in place that uses AmmoCount to determine if a bullet can be fired.

2. Create Ammo Pickup Blueprint
      * Go to the Content Browser → Right-click → Blueprint Class → Select Actor → Name it BP_AmmoPickup.
 * Add components:
       * Static Mesh: Representing the ammo (e.g., a bullet or crate).
       *  Sphere Collision: To detect overlap with the player.
  * In the Event Graph of BP_AmmoPickup:
       * Use OnComponentBeginOverlap on the Sphere Collision.
      * Cast to PlayerCharacter.
        * Increase the player’s AmmoCount (e.g., AmmoCount += 5).
         * Optionally, play a pickup sound or effect.
         * Destroy the ammo pickup actor.
3. Update Shooting Logic (Optional)
    * In your player’s shooting logic:
     * Before spawning a bullet, check if AmmoCount > 0.
        * If true:
         * Spawn bullet.
          * Decrease AmmoCount by 1.
4. Place Ammo in the World
* Drag instances of BP_AmmoPickup into your level from the Content Browser.
* Adjust position, mesh, and pickup range as needed.
  
# OUTPUT
<img width="1918" height="856" alt="image" src="https://github.com/user-attachments/assets/2309d916-4852-4f56-9c8d-8477f7df0f56" />
<img width="1335" height="839" alt="image" src="https://github.com/user-attachments/assets/0d04922f-8be8-4736-9763-32aeeb50eb65" />
<img width="1919" height="1013" alt="image" src="https://github.com/user-attachments/assets/aa3f059d-0165-464d-948e-ea174bb5c031" />
<img width="1134" height="765" alt="image" src="https://github.com/user-attachments/assets/befeb6b9-945c-4aa6-a474-2680dbd41320" />

# RESULT:
* The player starts with a limited number of bullets.
* When the player overlaps with an ammo pickup:
  * The ammo is collected.
  * The player's AmmoCount increases.
  * The player can now fire additional bullets based on the updated ammo count.
