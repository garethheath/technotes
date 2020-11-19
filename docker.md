# Docker notes

# docker compose

## project name

The default project name is the basename of the project directory. You can set a custom project name by using the -p command line option or the COMPOSE_PROJECT_NAME environment variable.




docker run \
    --name dataengine \
    --network midas \
    --publish 8081:80 \
    --detach \
    vanillanet

docker run \
    --name sql \
    --hostname sql \
    --network midas \
    --publish 1433:1433 \
    --detach \
    --env "ACCEPT_EULA=Y" \
    --env "SA_PASSWORD=Unbreakable.Password.123" \
    mcr.microsoft.com/mssql/server  

docker run \
    --name dnstools \
    --network midas \
    --detach \
    tutum/dnsutils sh


docker exec -it firstflight_db_1 "bash"

/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P "Unbr3akable.Passw0rd"

SELECT Name from sys.Databases
CREATE DATABASE TestDB
GO

USE TestDB
CREATE TABLE Inventory (id INT, name NVARCHAR(50), quantity INT)
INSERT INTO Inventory VALUES (1, 'banana', 150); INSERT INTO Inventory VALUES (2, 'orange', 154);
GO

SELECT * FROM Inventory WHERE quantity > 152;
GO

QUIT

docker run -it --network midas tutum/dnsutils sh


