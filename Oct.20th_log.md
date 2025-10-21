## Daily Log
### Time
- 2025-10-20

### Workload
- 1. Implement data flow module in backend of Android Dev
- 2. Design Movie list view
- 3. Apply navigation of Compose

### Problem shooting
#### 1. Import package of Android Apps
- Android's Gradle ecosystem already provides what Docker offers for dependency
- and version constrol - at **the build system level, not OS level**
```kotlin
    // libs.versions.toml, look up docs first
    // [plugins]
    kotlin-serialization = { id = "<package-name>", version.ref = "name" }
    // [libraries]
    kotlinx-serialization-json = { module = "...", version = "..." }
    // model-level build.gradle.kts
    alias(libs.plugins.kotlin.serialization)
    implementation(libs.kotlinx.serialization.json)
```

#### 2. Full process of parsing JSON
- **1) Set up dependencies:**
- ensure ability to parse JSON and conncect ViewModels to Composables
- **2) Define the data model**
- create a **@Serializable data class**
- keep this model pure data - no Android-specific logic
- **3) Read and parse JSON in ViewModel**
- use openRawResourece(R.raw.details) -> read text(.bufferedReader().use{it.readText()}) -> Json.decodeFromString<>List<Movie>>()
- map poster and movie index to drawable IDs
- Expose the final lit via MutableStateFLow<List<Movie>>, initialize _movie.value
- **4) Display data in Compose UI**
- use collectAsSatate() to observe viewModel.movies
- **5) Handle errors**
- Optional: use ViewModelScope launch if JSON is read asynchronously

#### 3. NavHost
- **startDestination** = "list"
- **click event in MovieFragment:**
```kotlin
    onClick = { navController.navigate("details/${movie.id}") }
```
- **detailss screen reads movieId**
```kotlin
    val movieId = backStackEntry.argument?.getString("movieId")?.toInt()
    val movie = viewModel.movies.collectAsState().value.find{ it.id == movieId }
```