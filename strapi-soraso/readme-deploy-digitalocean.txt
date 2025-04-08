Updating a Strapi content type on a production server hosted on DigitalOcean involves several steps. Here's a general guide to help you through the process:

### Prerequisites

1. **Access to DigitalOcean server**: Ensure you have SSH access to your DigitalOcean server.
2. **Strapi project running on DigitalOcean**: Make sure your Strapi project is correctly set up and running on your DigitalOcean server.
3. **Backup**: Always take a backup of your database and current project before making any changes.

### Steps

1. **Connect to your DigitalOcean server**:
    ```sh
    ssh root@your_server_ip
    ```

2. **Navigate to your Strapi project directory**:
    ```sh
    cd /home/thanapol/strapi/strapi-soraso
    ```

3. **Update your content type locally**:
    - It's recommended to make changes to your content type on your local development environment first.
    - Once you've made the necessary changes, test them thoroughly to ensure they work as expected.

4. **Push changes to your version control system** (e.g., GitHub):
    ```sh
    go to database and server config to check
    git add .
    git commit -m "Update content type"
    git push origin main
    ```

5. **Pull changes on your DigitalOcean server**:
    ```sh
    git pull origin main
    ```

6. **Install any new dependencies**:
    If your changes include new dependencies, install them:
    ```sh
    npm install
    ```

7. **Build the Strapi project**:
    ```sh
    npm run build
    ```

    login as thanapol to see pm2 using 'su thanapol'
    ```sh

8. **Restart your Strapi server**:
    Depending on how you have set up your Strapi project (e.g., using PM2, Docker, etc.), restart the server to apply the changes. For example, with PM2:
    ```sh
    pm2 restart strapi-app
    ```

    If using Docker:
    ```sh
    docker-compose down
    docker-compose up -d
    ```

9. **Verify your changes**:
    Ensure the changes have been applied correctly by checking your Strapi admin panel and testing the updated content type.

### Important Notes

- **Database Migrations**: If your content type changes include database migrations, ensure that these migrations are properly handled.
- **Environment Variables**: Make sure any new environment variables required by your changes are set correctly on your production server.

If you encounter any issues or need specific commands for your setup (e.g., using Docker or a specific deployment strategy), feel free to ask!


