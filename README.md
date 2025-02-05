# blog

Ensure following setting is turned on
	Settings => Editor => All pages public when publishing

... => Export Graph => Export public pages to /blog


docker build . -t blog

docker run -it -p 8080:80 blog

deployed on Netlify