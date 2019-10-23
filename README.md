# zawgyi-unicode-file-converter

I created a simple script to convert text files in Zawgyi to Unicode, as I couldn't find one in existence. There are plenty of online converters where you paste in a piece of text in ZG and it'll produce a Unicode version. This is fine, if all you have is a paragraph or a page or two to convert. But if you have many files over 10s or 100s of pages then this type of conversion is not feasible to do it page by page or file per file manually.<p>

The zg2uni Python function code snippet used in the script comes courtesy of Rabbbit Conveter: https://github.com/Rabbit-Converter/Rabbit <p>

<b>Limitations:</b>
The script will only work with plain text files, i.e. .txt, .csv or .html. It will not work in .rtf, .docsx, .xlsx, etc. 

<b>Usage:</b><p>
<p>
><i>python zg-uni-file-converter.py -s {source directory} -d {destination dir. (optional)} -e {file extension (optional)} -n {name extension (optional)}</i>
<p>
This will scan the entire source directory and convert each file matching the extension to Unicode and save the new file in the destination directory, and appending the name extension the source file name.
<p>
<b>Example 1:</b> Convert all files from the source direcory and saves the converted files in a different directory having the same name as the original files.
<p>
/original  <br>
file_one.txt<br>
file_two.txt<br>

><i>python zg-uni-file-converter.py -s original -d converted  </i>

After running the script, the destination directory will contain:

/converted <br>
file_one.txt<br>
file_two.txt <br>

<b>Example 2:</b> Saves converted files in the same directory as the original but the converted files have different name extension added to the name.
<p>
/original  <br>
file_one.txt<br>
file_two.txt<br>

><i>python zg-uni-file-converter.py -s original -n uni</i>

After running the script, the original directory will contain:

/original<br>
file_one.txt<br>
file_one.uni.txt<br>
file_two.txt <br>
file_two.uni.txt <br>

<b>Example 3:</b> Convert only the files matching the extension type from the source directory. This is useful if you have a directory with a mixture of file types. In the example below, the script will only convert files of the type .txt. 
<p>
/original<br>
file_one.txt<br>
file_two.docx<br>
file_three.xlsx<br>
file_four.txt<br>
file_five.jpg<br>

><i>python zg-uni-file-converter.py -s original -d converted -e txt -n uni</i>

After running the script, the original directory will contain:

/converted <br>
file_one.uni.txt<br>
file_four.uni.txt <br>

<b>To Do:</b>
Extend the directory scanner to parse through the entire sub-directory tree and convert all files within them. This will be suitable for converting, for example, an entire website written in ZG by converting all HTML files.


