This is related to setting up a custom domain for github pages. My published site was working fine, e.g. mysite-ai.github.io . I then configured my company domain, mysite.ai to point to my published site. I can no longer see my published site and the urls for both mysite.ai and mysite-ai.github.io timeout. Shouldn't mysite-ai.github.io still be visible? WHen I go to mysite-ai.github.io repository -> pages, it no longer shows that it is active. When I go to Actions, it shows that the last push deployed to mysite.ai. WHen I run dig I get this response

;; ANSWER SECTION:
mysite.ai. 600 IN A 185.199.110.153
mysite.ai. 600 IN A 185.199.11.153
mysite.ai. 600 IN A 15.197.142.173
mysite.ai. 600 IN A 3.33.152.147
mysite.ai. 600 IN A 185.199.108.153
mysite.ai. 600 IN A 185.199.109.153

At my DNS provider, I added an A record to get the above result, and a TXT record to be able to do verification. Domain verification for my github organization mysite-ai succeeds. The Pages tab under the repository mysite-ai.github.io does NOT show a domain. When I add mysite.ai as a custom domain I get :

Both mysite.ai and its alternate name are improperly configured
Domain does not resolve to the GitHub Pages server. For more information, see [documentation]
(https://docs.github.com/articles/setting-up-a-custom-domain-with-github-pages/) (NotServedByPagesError).

I cannot find the NotServedByPagesError info on the page mentioned above.

When I visit the website I get an error

Your connection is not private net::ERR_CERT_COMMON_NAME_INVALID

When I click through the error I get a 404 There isn't a GitHub Pages site here

I've added an HTTP record that points to mysite-ai.github.io.

Anyone know how to figure out what the solution is to get this site running?

-----
Solution:


1) Only the github organization needs to be verified.  Also verifying fondata.ai from jmagosta (my personal account)
under "pages" confuses github and forces periodic unverifing.

2) A commit pull - push cycle is necessary to re-set the static github site (Error is a 404 from github)
