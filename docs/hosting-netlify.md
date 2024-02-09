# Netlifyへのホスト

ここでは [](hosting-rtd) で作成したリポジトリを使って、Netlifyにホストします。

[Netlify](https://app.netlify.com/) にログインし、「Add new site」から「Import an existing project」をクリックします。

![](./images/netlify-add-new-site.png)

「Deploy with GitHub」をクリックします。

![](./images/deploy-with-github.png)

作成したリポジトリを選択して、クリックします。

![](./images/lets-deploy-your-project.png)

下記の項目を入力し、「Deploy site-name」をクリックします（site-nameは、下記で指定したSite name）。

- Site name: ほかと重複しない任意の名前
- Build command: `make html`
- Publish directory: `_build/html`

![](./images/review-configuration.png)

「Production deploys」が `Published` になったら、デプロイが完了です。「Production: main@HEAD Published」をクリックします。

![](./images/production-deploys.png)

「Published deploy for site-name」（site-nameは、指定したSite name）の「Open production depoy」をクリックすると、作成したサイトが表示されます。

![](./images/published-deploy.png)