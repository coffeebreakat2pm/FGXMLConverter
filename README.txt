FG XML Converter
================

Converts COINS insurance XML files to FG Healthcare Excel files
(BMS_SWEDEN_<INSURANCE>_DDMMYYYY.xlsx, one file per insurance name;
Swedish letters ÅÄÖ become AAO in file names).
All processing happens locally on your computer - nothing is uploaded anywhere.

Starting the app the first time
-------------------------------
1. Unzip the folder anywhere (right-click the ZIP -> "Extract All...").
2. Double-click FGXMLConverter.exe.
3. Windows may show a "Windows protected your PC" warning because this app is
   not signed. If "More info" and "Run anyway" are available, choose them to
   continue. Some work or school computers block unsigned apps; contact your
   IT team if Windows does not offer a way to continue.

How to use
----------
1. Start the application (FGXMLConverter.exe, or "python main.py" during development).
2. Click "Select XML files..." and pick one or more .xml files, or simply
   drag .xml files from Windows Explorer and drop them onto the window -
   the file box highlights while you hover to show the drop will work.
3. The output folder defaults to your Downloads folder. Click "Browse..." if
   you want to choose a different folder; your last choice is remembered.
4. Click "Convert". The progress bar shows how many files are done.
5. When finished, the summary lists each produced Excel file and any errors.
   Files that converted successfully are kept even if another file failed.
6. Click "Open output folder" to open the results in Windows Explorer.

Existing output files are never overwritten - a " (1)", " (2)", ... suffix is
added instead.

Running from source (developers)
--------------------------------
    python -m pip install -r requirements.txt
    python main.py

Run the tests:
    python -m unittest discover tests

Building the portable Windows package (developers)
--------------------------------------------------
In a clean virtual environment on Windows:

    python -m pip install -r requirements.txt
    python -m pip install pyinstaller
    python -m PyInstaller --noconfirm FGXMLConverter.spec

Then ZIP the entire dist\FGXMLConverter folder and deliver it. Test the
packaged FGXMLConverter.exe on a machine without Python installed.

Reporting issues
----------------
Note the XML file name and the exact error text shown in the summary area,
and send them to your application contact. Do not send personal data unless
your organisation's policies allow it.

License notices
---------------
This application uses the following open-source libraries:
- CustomTkinter (MIT License) - https://github.com/TomSchimansky/CustomTkinter
- openpyxl (MIT License) - https://openpyxl.readthedocs.io
- tkinterdnd2 (MIT License) - https://github.com/pmgagne/tkinterdnd2
