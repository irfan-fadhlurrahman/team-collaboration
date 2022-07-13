## Materi buat Rabu, 13 Juli 2022
### Downloads
* Download **Windows Terminal** di Microsoft Store
* Download file menggunakan git bash: 
    ```
    curl <url> -O
    ```

### Git and GitHub    
* Personal token access: 
    ```
    Setting --> Scroll ke bawah --> Klik 'Developer' --> Personal Access Token --> 
    Klik 'Generate new token' --> Copy token dan paste di txt file
    ```
* Configure GitHub personal credentials in Git Bash
    ```
    # set your username
    git config --global user.name "FIRST_NAME LAST_NAME"
    ```
    
    ```
    # set your github email
    git config --global user.email "MY_NAME@example.com"
    ```
* Download seluruh file di repository
    ```
    git clone <repository_link>
    ```
    
    ```
    # i.e. download `team-collaboration` repository
    git clone https://github.com/irfan-fadhlurrahman/team-collaboration.git
    ```
* Bikin branch
    ```
    git branch <branch_name>
    ```
* Pindah branch
    ```
    git checkout <branch_name>
    ```
* Cek ada branch apa saja
    ```
    git branch
    ```
* Cara pake git buat upload
    ```
    # add your file or folder
    git add <file_1> <file_2> ... <file n>
    
    # commit and write the information about the file changes
    git commit -m "<your_information_about_changes>"
    
    # optional: if you commit to 'main' branch, try to update the local repo first
    git pull origin main
    
    # notes: if you commit to 'personal_branch` branch, no need to pull
    # but if there is changes in your online repository i.e. delete or add a file
    # in your own branches through browser, you need to 'pull' first before 'push'
    git push origin <branch_name>
    
    # somewhere you need to enter your github username and personal token access
    ```

### Case Study with SQL and Python

**Dataset**: NYC Yellow Taxi Trip Data at January 2021.

1. Bahas cara nambahin kolom duration
2. Bahas data dictionary: https://www1.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf
3. Problem statement? Predict durasi atau fare? Masalah macet di NYC: traffic congestion problems
4. Apakah data sudah lengkap? data yang digunakan apa saja?
5. Referensi EDA: 
https://www.analyticsvidhya.com/blog/2021/01/exploratory-data-analysis-on-nyc-taxi-trip-duration-dataset/
6. EDA (univariate) & insight pake SQL
    * Cek jumlah rows
    * Cek jumlah kolom: https://stackoverflow.com/questions/658395/find-the-number-of-columns-in-a-table#:~:text=Query%20to%20count%20the%20number,of%20columns%20you%20want%20returned.
    * Cek jumlah missing values
    * Cek data types
    * Cek summary statistics
    * Data quality issue? need filtering the data?
    * Cek distribusi
    * What is the most crowded pickup and dropoff location? Most common route?
    * When is the busiest hour?
    * Does the surge happen in the busiest hour?

7. EDA multivariate pake Python or SQL?
8. Feature engineering?
    * Pickup: minutes, hours, day, month, day of week, weekend, night
    * Duration in minutes
    * Location: pickup, dropoff
