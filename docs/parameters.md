Based on the `Args` struct in the provided main.zig code, this program accepts the following parameters.

---

### **Required Credentials / Inputs**

The program requires at least one of these to run (unless you are checking the version):

* **`access_token`** (String): Your GitHub personal access token used to fetch data from the GitHub API.
* **`json_input_file`** (String): Path to a local JSON file containing pre-fetched statistics (can be set to `"-"` to read from `stdin`).

---

### **Output Configuration**

* **`json_output_file`** (String): Path where the fetched GitHub statistics will be cached/saved as JSON.
* **`overview_output_file`** (String): Path to save the generated overview SVG (Defaults to `"overview.svg"`).
* **`languages_output_file`** (String): Path to save the generated language distribution SVG (Defaults to `"languages.svg"`).

---

### **Filtering & Constraints**

* **`exclude_repos`** (String): A list of repositories to skip, separated by commas, spaces, or pipes. Supports glob matching.
* **`exclude_langs`** (String): A list of programming languages to exclude from the breakdown.
* **`exclude_private`** (Boolean): If set to `true`, private repositories will be ignored.
* **`max_retries`** (Integer): Maximum number of retries for GitHub API calls (Defaults to `25`).

---

### **Templating**

* **`overview_template`** (String): Path to a custom SVG template for the overview stats.
* **`languages_template`** (String): Path to a custom SVG template for the language stats.
* **`dump_overview_template`** (String): Path where the program will write its embedded default overview template, then exit.
* **`dump_languages_template`** (String): Path where the program will write its embedded default language template, then exit.

---

### **Logging & Core Flags**

* **`silent`** (Boolean): Suppresses most logging, forcing the log level to `.err`.
* **`verbose`** (Boolean): Enables detailed informational logging (`.info`).
* **`debug`** (Boolean): Enables full debug logging (`.debug`).
* **`version`** (Boolean): Prints the application version info and exits immediately.
