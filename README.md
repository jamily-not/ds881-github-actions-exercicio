# Exercício Github Actions: Validação de Pull Requests

**Objetivo:** configurar um workflow que impede a quebra de código na ramificação principal, validando os testes automatizados diretamente na abertura de um Pull Request.

## Instruções
1.  Faça um fork do repositório base.
2.  Crie uma nova branch na sua máquina local (ex: `git switch -c feature-correcao`).
3.  Crie o arquivo `.github/workflows/pr-check.yml`.
4.  Configure o workflow para ser disparado **apenas** quando houver atividade do tipo `pull_request` apontando para a branch `main`.
5.  O job deve usar o `ubuntu-latest`, fazer o checkout do código, instalar o Python, instalar o `pytest` via arquivo `requirements.txt` e executar o comando `pytest`.
6.  Faça o commit destas alterações e suba a branch para o seu fork.
7.  Abra um Pull Request no GitHub.
8.  **Validação 1:** Observe a aba "Checks" do Pull Request. O workflow deve rodar e falhar, pois o método `subtrair` está com erro lógico. O GitHub exibirá um "X" vermelho.
9.  **Validação 2:** Corrija a lógica do método `subtrair` (altere `a + b` para `a - b`), faça um novo commit e um `git push`. O PR será atualizado automaticamente, os testes passarão e o ícone ficará verde, sinalizando que é seguro realizar o Merge.
