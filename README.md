This project is study for hyperledger-fabric-practice

### fabcar -> usermanager !!

----- Edit chaincode -----<br>
```bash
cd ~/fabric-samples/chaincode/
cp -r fabcar usermanager
mv usermanager/go/fabcar.go usermanager/go/usermanager.go
```

// change usermanager.go<br>
```bash
nano usermanager/go/usermanager.go
```
Car -> User<br>
car -> user<br>
Make -> Firstname<br>
Model -> Lastname<br>
Colour -> Email<br>
Owner -> Phone<br>
make -> firstname<br>
model -> lastname<br>
colour -> email<br>
owner -> phone<br>
CAR -> USER<br>

--------------------------<br>


----- Edit usermanager -----<br>
```bash
cd ..
cp -r fabcar usermanager
cd usermanager
```

// change startFabric.sh<br>
```bash
nano startFabric.sh
```
fabcar -> usermanager<br>

// change query.js<br>
```bash
nano javascript/query.js
```
line 41 // const result = await contract.evaluateTransaction('queryUser', 'USER5');<br>
add - const result = await contract.evaluateTransaction('queryAllUsers');<br>

fabcar -> usermanager<br>
Car -> User<br>
CAR -> USER<br>

// change invoke.js<br>
```bash
nano javascript/invoke.js
```
mod - await contract.submitTransaction('createUser', 'USER5', 'Ahn', 'jongmin', 'ggg@ggg.com', '010-7777-7777'); 

fabcar -> usermanager<br>
Car -> User<br>
CAR -> USER<br>
Owner -> Phone<br>

----------------------------<br>


----- run -----<br>
```bash
cd javascript
npm install
cd ..
./startFabcar.sh

cd javascript
node enrollAdmin.js
node registerUser.js
node query.js
node invoke.js
```

---------------<br>


=====================================================================



[//]: # (SPDX-License-Identifier: CC-BY-4.0)

## Hyperledger Fabric Samples

Please visit the [installation instructions](http://hyperledger-fabric.readthedocs.io/en/latest/install.html)
to ensure you have the correct prerequisites installed. Please use the
version of the documentation that matches the version of the software you
intend to use to ensure alignment.

## Download Binaries and Docker Images

The installation instructions will utilize `scripts/bootstrap.sh` (available in the fabric repository)
script to download all of the requisite Hyperledger Fabric binaries and docker
images, and tag the images with the 'latest' tag. Optionally,
specify a version for fabric, fabric-ca and thirdparty images. If versions
are not passed, the latest available versions will be downloaded.

The script will also clone fabric-samples repository using the version tag that
is aligned with the Fabric version.

You can also download the script and execute locally:

```bash
# Fetch bootstrap.sh from fabric repository using
curl -sS https://raw.githubusercontent.com/hyperledger/fabric/master/scripts/bootstrap.sh -o ./scripts/bootstrap.sh
# Change file mode to executable
chmod +x ./scripts/bootstrap.sh
# Download binaries and docker images
./scripts/bootstrap.sh [version] [ca version] [thirdparty_version]
```

### Continuous Integration

Please have a look at [Continuous Integration Process](docs/fabric-samples-ci.md)

## License <a name="license"></a>

Hyperledger Project source code files are made available under the Apache
License, Version 2.0 (Apache-2.0), located in the [LICENSE](LICENSE) file.
Hyperledger Project documentation files are made available under the Creative
Commons Attribution 4.0 International License (CC-BY-4.0), available at http://creativecommons.org/licenses/by/4.0/.
