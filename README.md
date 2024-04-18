# secure_encryption_of_data

Adding and updating [other user information] in GitHub files, using REST API PUT/POST/PATCH, requires that the web application have permission to modify information and that the information is protected/encrypted for user protection. 

A web application has permission to modify Github file information using the GitHub API, with GitHub Secrets and GitHub Actions. The data sent and obtained using REST API, between the web application and the GitHub Server/Actions, is encoded in base64 format to protect user data while the data is sent. However, eventhough GitHub repository file data is protected/encoded while the data is sent over the Internet the data in a GitHub repository file is typically humanly readable. Thus, to further protect GitHub repository file data one can encode the data stored in a file using public-private data encryption methods.

The webapp below converts string data to and from base64, for rapid usage. The webapp also generates public-private data encryption keys in JSON Web Key format, for manual insertion into GitHub Secrets; similar to how GitHub generates tokens for access to GitHub resources. Using GitHub Actions, one can use the keys to: decrypt GitHub repository file data, then perform simple transformations on the data, then re-encrypt the data, and PUT/POST/PATCH the encrypted data back to the GitHub repository file.

[A working version of how to convert strings to different encoding formats (base64, ASCII or byteArray) and a public-private data encryption key generator] https://codesolutions2.github.io/secure_encryption_of_data/encode_decode_data.html
