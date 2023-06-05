# chatgpt
Incluindo o chatgpt dentro de um código python
import openai

def autenticar_openai():
    openai.api_key = 'SUA_CHAVE_DE_API_OPENAI'

def gerar_resposta(mensagem):
    resposta = openai.Completion.create(
        engine='text-davinci-003',
        prompt=mensagem,
        max_tokens=50,
        temperature=0.7,
        n=1,
        stop=None,
        temperature=0.7
    )
    return resposta.choices[0].text.strip()

def main():
    print("Bem-vindo ao ChatGPT!")
    autenticar_openai()

    while True:
        mensagem = input("Usuário: ")

        # Encerrar o chat se o usuário digitar "sair"
        if mensagem.lower() == "sair":
            print("Chat encerrado.")
            break

        # Gerar resposta utilizando o ChatGPT
        resposta = gerar_resposta(mensagem)

        # Exibir a resposta gerada
        print("ChatGPT: ", resposta)

if __name__ == "__main__":
    main()
