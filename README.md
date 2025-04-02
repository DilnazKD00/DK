pip install pyodbc
import pyodbc

# Azure SQL Database параметрлері
server = 'my-sql-server.database.windows.net'  # Өз серверіңізді жазыңыз
database = 'my-sql-db'  # Дерекқордың аты
username = 'adminuser'  # Логин
password = 'Admin123!'  # Құпиясөз
driver = '{ODBC Driver 17 for SQL Server}'

# Дерекқорға қосылу
try:
    conn = pyodbc.connect(
        f'DRIVER={driver};SERVER={server};PORT=1433;DATABASE={database};UID={username};PWD={password}'
    )
    cursor = conn.cursor()
    print("Azure SQL Database-ке сәтті қосылдық!")

    # Дерекқордан мәлімет оқу
    cursor.execute("SELECT name FROM sys.databases")
    rows = cursor.fetchall()

    print("Дерекқор тізімі:")
    for row in rows:
        print(row[0])

    # Байланысты жабу
    conn.close()
except Exception as e:
    print("Қате пайда болды:", e)
    pip install azure-storage-blob
    from azure.storage.blob import BlobServiceClient

# Azure Storage параметрлері
connection_string = "DefaultEndpointsProtocol=https;AccountName=myblobstorage123;AccountKey=your_account_key;EndpointSuffix=core.windows.net"
container_name = "mycontainer"
blob_name = "example.png"
file_path = "example.png"

try:
    # Storage клиентін жасау
    blob_service_client = BlobServiceClient.from_connection_string(connection_string)
    blob_client = blob_service_client.get_blob_client(container=container_name, blob=blob_name)

    # Файлды жүктеу
    with open(file_path, "rb") as data:
        blob_client.upload_blob(data, overwrite=True)

    print(f"Файл {blob_name} сәтті жүктелді!")
except Exception as e:
    print("Қате пайда болды:", e)
    git init
git remote add origin https://github.com/your_username/azure-cloud-project.git
git add .
git commit -m "Azure жобасы үшін дайын кодтар"
git push origin main
