# Test Data Documentation

## Folder layout

```
tests
│   defaults.json                        # Global defaults for the tests
│   README.md                            # This README
│   test_cases_schema.csv                # The CSV file to copy for each new species
│                                        # 
├───shared_data                          # Test audio files common to more than one species 
│                                        # 
└───species                              # Each species we test has its own folder
    ├───Exempli_gratia                   # 
    │   │   test_cases.csv               # One or more test case CSV files must be in each folder
    │   │   README.md                    # A README to document test sources
    │   │                                # 
    │   └───data                         # Test audio files for a species
    │           Exempli_gratia_1.flac    # Test audio file - name does not matter 
    │                                    # 
    └───Rhinella_marina                  # ...repeat....
        │   test_cases.csv               # 
        │   README.md                    # 
        └───data                         # 
                2015-06-03-004248.wav    # 
                README.md                # 
```

## Instructions

### To test a new species

1. Create a new folder within the `species/` directory
2. Name the folder with the full latin name of the species, replace spaces with underscores
  - e.g. `Exempli_gratia`
  - e.g. `Rhinella_marina`
3. Open your new species folder
4. Create a `README.md` text file
5. Copy the `test_cases_schema.csv` file into the species folder. Rename it to `test_cases.csv`
6. Create a new folder called `data` inside your species folder

### Add a new test case

1. Add at least one example file for the species into the `data` folder
1. Add a row to the `test_cases.csv` file

## SUPER IMPORTANT THINGS

- Ensure binary files you add are added to _git lfs_ (git Large File Storage). If you're unsure, ask!
- Where possible add test cases in the _FLAC_ (Free Lossless Audio Codec) to save space

## Converting files to FLAC

Open a prompt that has the `ffmpeg` program on PATH.

Change directory to the directory that has your source file (using the `cd` command).

Then run:

```
> ffmpeg -i input_file.wav output_file.flac 
```

Replace `input_file.wav` with the file you wish to convert and `output_file.wav` with the name of 
the new file you wish to write.

### Installing ffmpeg

1. Install _Chocolatey_ if you haven't already: https://chocolatey.org/install
2. In an elevated shell (e.g. PowerShell running as Adminsitrator), type
  ```
  > choco install ffmpeg
  ```

3. Restart your shell if needed