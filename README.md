### Prerequisites(Ubuntu O.S.)
- Docker and Docker compose installed
# Install and Configure Setup
sudo apt update
sudo apt upgrade -y
sudo apt install -y ca-certificates curl gnupg lsb-release
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
  sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch=$(dpkg --print-architecture) \
  signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo usermod -aG docker $USER
sudo chmod 666 /var/run/docker.sock
# After Installation & configuration 
docker compose up -d
# Check Images and containers are running 
docker images
docker ps

# if you want to run without docker 
cd client && npm install
npm start
cd server && npm install
npm start

<hr>

As organs are needed ASAP for operations, time is the most crucial aspect. However, the existing method to request organs from procurement centre/ transplant centres is completely manual (manual data entry, manual communication via faxes, mails, phone calls) and thus is obviously error prone and time consuming. Therefore to solve this grave issue, 'OrganEase' is proposed. 

The website makes the tedious manual task of categorizing different organs and making entries for each, mere clicks away. In a particular region, say n number of procurement centres and/or transplant centres exist. All of them can display the organs stored in their hypothermic storages along with their details at one time (this completely solvesthe time-consuming problem of individually calling of procurement centres one by one which is done presently). 

Hospitals can request organs of suitable compatibility (Blood Group, etc) via the portal itself and make a payment which serves as a token of confirmation for the transfer procedure. Thereafter, the procurement centre has the option to confirm the request from their side.


Special Thanks & Credit to this project **Kartik Katkar**
**https://github.com/Kartik-Katkar**
Original Repository 
**https://github.com/Kartik-Katkar/OrganEase**
