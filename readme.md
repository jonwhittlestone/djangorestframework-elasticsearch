# Django DRF Elasticsearch Example

A dockerized example of a django app that serves Elasticsearch results as REST endpoints via Django Rest Framework

For query examples, refer to: django-elasticsearch-dsl-drf docs

https://django-elasticsearch-dsl-drf.readthedocs.io/en/0.15/advanced_usage_examples.html#search

## Steps to run

1. Bring up the dockerized services

   `docker-compose up --build`

2. Run the migrations to create and seed the database for Django and the `Article` app

   `docker exec -it elastic_drf_example_django python manage.py migrate`

3. Create a superuser

   `docker exec -it elastic_drf_example_django python manage.py createsuperuser`

4. Create some dummy data in django admin

   `http://localhost:8000/admin/articles/article/add/`

5. Create the search index, and populate the article data

   `docker exec -it django_elastic_drf_example_django python manage.py search_index --create`

6. Examples

   `http://0.0.0.0:8000/articles/?search=title|New - find articles containing the ‘New’ value in their titles,`

## Troubleshooting

- Are the 3 docker containers all running?
