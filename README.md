
Installation information
=======

This template repository can be directly cloned to get you started with a new
mod. Simply create a new repository cloned from this one, by following the
instructions provided by [GitHub](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template).

Once you have your clone, simply open the repository in the IDE of your choice. The usual recommendation for an IDE is either IntelliJ IDEA or Eclipse.

If at any point you are missing libraries in your IDE, or you've run into problems you can
run `gradlew --refresh-dependencies` to refresh the local cache. `gradlew clean` to reset everything 
{this does not affect your code} and then start the process again.

Mapping Names:
============
By default, the MDK is configured to use the official mapping names from Mojang for methods and fields 
in the Minecraft codebase. These names are covered by a specific license. All modders should be aware of this
license. For the latest license text, refer to the mapping file itself, or the reference copy here:
https://github.com/NeoForged/NeoForm/blob/main/Mojang.md

Additional Resources: 
==========
Community Documentation: https://docs.neoforged.net/  
NeoForged Discord: https://discord.neoforged.net/

Release workflow setup
==========
The release workflow always builds the mod and publishes a GitHub Release. CurseForge and Modrinth publishing are optional and only run when their repository variable is set.

In the GitHub repository, go to Settings -> Secrets and variables -> Actions.

Add repository variables on the Variables tab:

- `CURSEFORGE_PROJECT_ID`: optional CurseForge project ID. Leave unset to skip CurseForge.
- `MODRINTH_PROJECT_ID`: optional Modrinth project ID or slug. Leave unset to skip Modrinth.
- `CURSEFORGE_DEPENDENCIES`: optional mc-publish dependency list for CurseForge.
- `MODRINTH_DEPENDENCIES`: optional mc-publish dependency list for Modrinth.
- `MOD_LOADERS`: optional loader list. Defaults to `neoforge`.
- `MINECRAFT_GAME_VERSIONS`: optional Minecraft version list. Defaults to `minecraft_version` from `gradle.properties`.
- `JAVA_VERSIONS`: optional Java version list. Defaults to `21`.

Add repository secrets on the Secrets tab only for the platforms you enabled:

- `CURSEFORGE_TOKEN`: required if `CURSEFORGE_PROJECT_ID` is set.
- `MODRINTH_TOKEN`: required if `MODRINTH_PROJECT_ID` is set.

Project IDs are variables because they are not sensitive. API tokens are secrets because they can publish files to your projects.
