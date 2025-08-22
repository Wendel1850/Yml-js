# Yml-phyton django
from django.contrib import messages
from django.shortcuts import redirect
from .models import MeuModelo

def criar_registro(request):
    if request.method == 'POST':
        form = MeuForm(request.POST)
        if form.is_valid():
            form.save()
            messages.success(request, 'Registro criado com sucesso!')
            return redirect('nome_da_url')
    else:
        form = MeuForm()
    return render(request, 'meu_template.html', {'form': form})
