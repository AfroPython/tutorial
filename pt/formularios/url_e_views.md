## URL

Vamos abrir o arquivo `blog/urls.py` e escrever:

blog/urls.py
```python
url(r'^post/new/$', views.post_new, name='post_new'),
```

O código final deve se parecer com isso:

blog/urls.py
```python
from django.conf.urls import url
from . import views

urlpatterns = [
    url(r'^$', views.post_list, name='post_list'),
    url(r'^post/(?P<pk>\d+)/$', views.post_detail, name='post_detail'),
    url(r'^post/new/$', views.post_new, name='post_new'),
]
```

Após atualizar o site, nós veremos um `AttributeError`, já que nós não ainda temos a view `post_new` implementada. Vamos adicioná-la agora.

## A view post_new

Hora de abrir o arquivo `blog/views.py` e adicionar as linhas seguintes com o resto das linhas `from`:

blog/views.py
```python
from .forms import PostForm
```

e então a nossa *view*:

blog/views.py
```python
def post_new(request):
    form = PostForm()
    return render(request, 'blog/post_edit.html', {'form': form})
```

Para criar um novo formulário `Post`, nós devemos chamar `PostForm()` e passá-lo para o template. Nós voltaremos para esta *view*, mas por agora, vamos criar rapidamente um template para o formulário.