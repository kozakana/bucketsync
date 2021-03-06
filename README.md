# bucketsync

Sync with s3bucket easily.

## Dependence

s3cmd

<pre>
#example

brew install s3cmd
</pre>

### s3cmd

recommend higher than 1.5

## Usage

<pre>
wget https://raw.githubusercontent.com/kozakana/bucketsync/master/bucketsync
chmod u+x bucketsync
./bucketsync ACCESSKEY SECRETKEY SYNCDIR BUCKETNAME
</pre>

## Command

<pre>
bucketsync [--help | --env | --dry-run | --no-ignore | --ignore=VALUE] ACCESSKEY SECRETKEY SYNCDIR BUCKETNAME
</pre>

## Options
<pre>
  -h, --help     show this help message and exit
  -e, --env      input access key, secret key, syncdir and bucket name from '.env' file
  --dry-run      Only show what should be uploaded or downloaded but
                 don't actually do it. May still perform S3 requests to
                 get bucket listings and other information though (only
                 for file transfer commands)
  --no-ignore    all files are targeted for upload
  --ignore=VALUE set your ignore file
</pre>

## '.env' file [option]

put your working folder.

<pre>
S3_ACCESS_KEY = 'AK1234556'
S3_SECRET_KEY = 'DFEWAefwj381012'
</pre>
OR
<pre>
S3_ACCESS_KEY = 'AK1234556'
S3_SECRET_KEY = 'DFEWAefwj381012'
DEPLOY_DIR = './public/'
S3_BUCKET_NAME = 'bucket_name'
</pre>

## Examples

<pre>
  bucketsync AK1234556 DFEWAefwj381012 ./public/ sample-bucket
  bucketsync -e ./public/ sample-bucket
  bucketsync -e
  bucketsync --dry-run AK1234556 DFEWAefwj381012 ./public/ sample-bucket
</pre>
