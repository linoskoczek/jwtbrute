# JwtBruteCore

JwtBruteCore takes a new line delimited list of canidate secrets in via stdin or from the file with passwords and tests them against a provided json web token to see if they were the secret used in the signing of the token. If the secret is discovered one can sign arbitry jwt tokens to bypass the authentication process of most webservices.

This version is made with .NET Core, so it can run on any platform with .NET Core installed.

## Install

```
git clone https://github.com/linoskoczek/jwtbrute.git
cd jwtbrute
dotnet restore
dotnet publish -c release --self-contained --runtime linux-x64 --framework netcoreapp2.2
```

## Usage examples

**password via stdin:**
```
echo secret| ./JwtBruteCore eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOjEyMzQ1Njc4OTAsIm5hbWUiOiJKb2huIERvZSIsImFkbWluIjp0cnVlfQ.eoaDVGTClRdfxUZXiPs3f8FmJDkDE_VCQFXqKxpLsts
```
Output:
> Secret was: secret

**file with passwords:**
```
./JwtBruteCore eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOjEyMzQ1Njc4OTAsIm5hbWUiOiJKb2huIERvZSIsImFkbWluIjp0cnVlfQ.eoaDVGTClRdfxUZXiPs3f8FmJDkDE_VCQFXqKxpLsts /path/to/your/passwords/list.txt
```
Output:
> Secret was: secret

**dotnet run with passwords file**
```
dotnet run eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOjEyMzQ1Njc4OTAsIm5hbWUiOiJKb2huIERvZSIsImFkbWluIjp0cnVlfQ.eoaDVGTClRdfxUZXiPs3f8FmJDkDE_VCQFXqKxpLsts /path/to/your/passwords/list.txt
```
Output:
> Secret was: secret

## License of the original tool

The MIT License (MIT)

Copyright (c) 2014-2015 Jmaxxz

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
