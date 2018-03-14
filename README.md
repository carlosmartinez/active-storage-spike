# README

A spike of Rails 5.2 Active Storage using direct upload via Javascript.

Loosely based on a [Martian Chronicles post](https://evilmartians.com/chronicles/rails-5-2-active-storage-and-beyond).

Once cloned, it shouldn't require much setup, just the usual to get the app running:

```
bundle
rake db:migrate
```

To connect with your S3 bucket, you'll need to set your credentials:

`EDITOR="vim" rails credentials:edit`

Also set the bucket name in `config/storage.yml`.

You'll need to set CORS on the S3 bucket. Here's what all the tutorials do:

```
<?xml version="1.0" encoding="UTF-8"?>
<CORSConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">
<CORSRule>
  <AllowedOrigin>*</AllowedOrigin>
  <AllowedMethod>GET</AllowedMethod>
  <AllowedMethod>POST</AllowedMethod>
  <AllowedMethod>PUT</AllowedMethod>
  <AllowedMethod>DELETE</AllowedMethod>
  <MaxAgeSeconds>3000</MaxAgeSeconds>
  <AllowedHeader>*</AllowedHeader>
</CORSRule>
</CORSConfiguration>
```

Don't do that for a bucket that you care about, or you may find yourself reacquainted with your P45.
