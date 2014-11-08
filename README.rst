=========================
Boto 3 Sample Application
=========================
This application implements a drop video transcoder that lets
you easily convert media files by dragging and dropping them
on your computer. It makes use of the following services:

* AWS IAM
* Amazon S3
* Amazon SNS
* Amazon SQS
* Amazon Elastic Transcoder

The general flow of the program can be described as:

1. Ensure AWS setup / permissions
2. Watch a directory for new files
3. Upload new files to S3
4. Create a transcoder job for each input file
5. Poll for job completed SQS messages
6. Download transcoded files
7. Repeat steps 2-7 until user quits (``ctrl+c``)

Running the Sample Application
------------------------------
First, ensure that you have `Boto 3 <https://github.com/boto/boto3>`_
installed::

    pip install -r requirements.txt

Then you can run the transcoder. The first time it is run, it will
create a default configuration file for you in ``~/.autotranscode.json``::

    python transcoder.py

Edit the file to suit your local setup and then run the same
command again. Once the application is running, you can drag
and drop files into your source folder to have them transcoded
and downloaded to the destination folder.
