# Sentimentos-com-Language-Studio-no-Azure-AI
Analise o texto com o Language Studio

Neste exercício, você explorará os recursos do Azure AI Language analisando alguns exemplos de avaliações de hotéis. Você usará o Language Studio para entender se as avaliações são positivas ou negativas.

O Processamento de Linguagem Natural (PNL) é um ramo da IA que lida com a linguagem escrita e falada. Você pode usar a PNL para criar soluções que extraem significado semântico do texto ou da fala, ou que formulam respostas significativas em linguagem natural.

Por exemplo, suponha que a agente de viagens fictícia Margie’s Travel incentive os clientes a enviar avaliações para estadias em hotéis. Você pode usar o serviço de Idioma para identificar frases-chave, determinar quais comentários são positivos e quais são negativos, ou analisar o texto da revisão para menções de entidades conhecidas, como locais ou pessoas.

O Azure AI Language Service inclui análise de texto e recursos de PNL. Estes incluem a identificação de frases-chave no texto e a classificação do texto com base no sentimento.
Criar um recurso de linguagem

Você pode usar muitos recursos do Azure AI Language com um recurso de serviços de idioma ou IA do Azure. Existem alguns casos em que apenas um recurso de linguagem pode ser usado. Para o exercício abaixo, usaremos um recurso de linguagem. Se ainda não o fez, crie um recurso de idioma na sua subscrição do Azure.

    Em outra guia do navegador, abra o portal do Azure em https://portal.azure.com, entrando na conta Microsoft associada à sua assinatura do Azure.

    Clique no botão +Criar um recurso e procure o serviço de Idioma. Selecione criar um plano de serviço de idioma. Você será levado para uma página para selecionar recursos adicionais. Mantenha a seleção padrão e clique em Continuar para criar seu recurso.
    Na páginaCriar linguagem, configure-o com as seguintes configurações:
        Assinatura: Sua assinatura do Azure.
        Grupo de recursos: Selecione ou crie um grupo de recursos com um nome exclusivo.
        Região : Leste dos EUA.
        Nome : Digite um nome único.
        Nível de preços: Grátis F0 ou S se o F0 Grátis não estiver disponível
        Ao marcar esta caixa, reconheço que li e entendi todos os termos abaixo: Selecionado.
    Selecione Revisão + criar, em seguida, Criar e aguardar a conclusão da implantação.

Configurar seu recurso no Azure AI Language Studio

    Em outra guia do navegador, abra o Language Studio em https://language.cognitive.azure.com e entre.

    Quando solicitado com o Select um recurso do Azure, faça as seguintes configurações:
        Diretório do Azure: Diretório Padrão, o diretório que você está usando
        Assinatura do Azure: Selecione a subscrição que está a utilizar
        Tipo de recurso : Idioma
        Nome do recurso : selecione o recurso de serviço de idioma que você acabou de criar

Em seguida, selecione Concluído.

    ImportanteA partir de julho de 2023, os serviços de IA do Azure abrangem todos os serviços anteriormente conhecidos como Serviços Cognitivos e Serviços de IA Aplicada do Azure. Algumas interfaces de usuário ainda estão atualizando sua referência a partir deCognitive ServicesparaAzure AI services- A . (í a , , , , , í , . Os dois nomes referem-se ao mesmo tipo de recurso.

    Observação : Se você não for solicitado a escolher um recurso de idioma, pode ser porque você tem vários recursos de idioma em sua assinatura; nesse caso:

        Na barra no topo, se a página, seleccione Definições ( )
        Na página Configurações, veja a guia Recursos.
        Selecione o recurso que você acabou de criar e selecione Comutação. Certifique-se de que a identidade gerenciada seja Habilitada. Enable language resource.
        No topo da página, selecione Estúdio de Idiomas para retornar à página inicial do Language Studio.

Analisar avaliações em Language Studio

    Em um navegador da Web, navegue para o Language Studio em https://language.cognitive.azure.com.

    Na página de destino Bem-vindo ao Estúdio de Idioma, selecione a guia Classificar texto e selecione o bloco de opiniões de análise e minerar.

    Em Selecionar idioma de texto, selecione Inglês.

    Em Selecionar o recurso Azure, selecione o seu recurso.

    Em Insira seu próprio texto, faça o upload de um arquivo ou use um de nossos textos de exemplo, copie e cole a seguinte revisão:
    Código do código

     Tired hotel with poor service
     The Royal Hotel, London, United Kingdom
     5/6/2018
     This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.

    Marque a caixa para reconhecer que a demonstração incorrerá em uso e poderá incorrer em custos e selecione Executar.

    Revise a saída. Observe que o documento é analisado para sentimento, bem como para cada sentença. Selecione Sentença 1 para mostrar a análise de sentimento para essa frase.

Observe que há um sentimento geral seguido por pontuações próximas a três categorias, pontuação positiva, pontuação neutra, pontuação negativa. Em cada uma das categorias, é fornecida uma pontuação entre 0 e 1. Essas pontuações de confiança indicam a probabilidade de o texto fornecido ser um sentimento particular.

Selecione Sentença 1 novamente para fechar.

    Role para cima para selecionar Limpar caixa de texto e copiar e colar a seguinte revisão:
    Código do código

     Good Hotel and staff
     The Royal Hotel, London, UK
     3/2/2018
     Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.

    Selecione Executar. Revise a saída e revise o nível de sentimento e confiança.

    Selecione Limpar caixa de texto novamente e copie e cole a seguinte revisão:

        Muito barulhento e os quartos são minúsculos The Lombard Hotel, São Francisco, Estados Unidos 9/5/2018 (em inglês) Hotel está localizado na rua Lombard, que é uma rua muito movimentada SIX pista diretamente da Ponte Golden Gate. Tráfego desde o início da manhã até tarde da noite, especialmente nos fins de semana. O ruído não seria tão ruim se os quartos fossem melhor isolados, mas não são. Tive que colocar bolas de algodão nos meus ouvidos para poder dormir – estava cansado demais para aproveitar a cidade no dia seguinte. Os quartos são TINY. Eu escolhi o quarto porque tinha duas camas queen size – mas o quarto mal tinha espaço para encaixá-las. Com a família de quatro na sala, foi apertado. Com tudo isso dito, os quartos estão limpos e eles fizeram um esforço para atualizá-los. O hotel fica no bairro de Marina, com muitos bons lugares para comer, a uma curta distância a pé de Presidio. Pode ser um bom hotel para jovens adultos com um orçamento

    Selecione Executar e rever o sentimento junto com o nível de confiança. Dê uma olhada no texto e compare o texto com a análise de sentimento que o serviço retornou.

Neste exercício, você usou o Language Studio para criar um novo recurso de idioma ou usar um recurso de idioma existente. Você ativou o recurso em Configurações antes de experimentar o serviço de mineração de sentimento e opinião. Em seguida, você testou o serviço com três peças de texto.
Limpo para cima

Se você não pretende fazer mais exercícios, exclua os recursos que você não precisa mais. Isso evita acumular custos desnecessários.

    Abra o portal do Azure em https://portal.azure.com e selecione o grupo de recursos que contém o recurso que criou.
    Selecione o recurso e selecione Excluir e, em seguida, Sim para confirmar. O recurso é então excluído.

Saiba mais

Para saber mais sobre o que você pode fazer com este serviço, consulte a página de serviço de idiomas.


Explore o Estúdio de Fala

O serviço de fala AI do Azure transcreve o discurso em texto e o texto em um discurso sonoro. Você pode usar o AI Speech para criar um aplicativo que pode transcrever notas de reunião ou gerar texto a partir da gravação de entrevistas.

Neste exercício, você experimentará as capacidades do Azure AI Speech usando o Azure AI Speech Studio.
Criar um recurso de fala do Azure AI

Você pode usar o serviço de fala criando um recurso de fala ou um recurso de serviços de IA do Azure.

Neste exercício, você criará um recurso de fala de IA, a menos que você já tenha um recurso que você possa usar.

    Em outra guia do navegador, abra o Azure AI Speech Studio, entrando com sua conta da Microsoft.
    Select Configurações then Create a resource. Configure it with the following settings:
        Name of new resource: Enter a unique name.
        Subscription: Your Azure subscription.
        Region: Select a supported region.
        Pricing tier: Free FO (if available, otherwise select Standard S0).
        Resource group: Select or create a resource group with a unique name.
    Select Create resource. Wait until the resource has been created and then select Use resource. The Get started with Speech page is displayed.

Explore speech to text in Speech Studio

    Select https://aka.ms/mslearn-speech-files to download speech.zip. Open the folder.

    On the Get started with Speech page, under Speech to text find Real-time speech to text. Select Try out Real-time speech to text.

    Getting started with Speech

    Under Choose audio files, select Browse files and navigate to the folder where you saved the file. Select WhatAICanDo.m4a and then Open.

    Browse files
    The Speech service transcribes and displays the text in real time. If you have audio on your computer, you can listen to the recording as the text is being transcribed.

    Review the output, which should have successfully recognized and transcribed the audio into text.

        Note If you get an error message, wait a few minutes before trying again. It takes a little time for the Speech resource to be available for first use.

In this exercise you created an AI Speech resource in Speech Studio. You then used the Real-time speech to text service to transcribe an audio recording. You were able to see the text transcription being generated as the audio file was played.
Clean up

If you don’t intend to do more exercises, delete any resources that you no longer need. This avoids accruing any unnecessary costs.

    Open the Azure portal and select the resource group that contains the resource you created.
    Select the resource and select Delete and then Yes to confirm. The resource is then deleted.

Learn more

This exercise demonstrated only some of the capabilities of the Speech service. To learn more about what you can do with this service, see the Speech page.
