## Implementação da seção 9.5 do Dive into Deep Learning e resposta do exercícios

1. Tente valores diferentes do argumento num_examples na funçãoload_data_nmt. Como isso afeta os tamanhos do vocabulário do idioma de origem e do idioma de destino?


>`'num_examples'` é o número de frases. Quanto maior o número nesse parâmetro, maior o número de frases do dataset serão usadas no treinamento. Com mais frases, maior o vocabulário, posto que quanto mais frases usamos, mais palavras diferentes aparecem (aumentando o número de tokens).
>
> Ao usar 600 exemplos, o vocabulário de origem tem 184 tokens e o de destino 201 tokens; com 1.200 exemplos, 314 e 384; com 6.000 exemplos, 1.037 para origem 1.454 para o destino. Isso aumenta o número de palavras conhecidas, mas também aumenta o custo computacional. Ademais, com esses testes, nota-se que o crescimento do vocabulário foi mais relevante ao dobrar o número de frases e mais suave ao fazer 10x, mostrando que o crescimento não é linear. 



2. O texto em alguns idiomas, como chinês e japonês, não tem indicadores de limite de palavras (por exemplo, espaço). A tokenização em nível de palavra ainda é uma boa ideia para esses casos? Por que ou por que não?

>Por possuirem sistemas linguísticos diferentes, não podemos aplicar as mesmas regras que usamos nas línguas ocidentais. Não faz sentido analisar da mesma forma, posto que não há com identificar palavras a partir do espaço. Nessas línguas com ideogramas, o ideal é identificar cada ideograma, o que pode ser feito analisando cada caractere.
>
>Para cada língua, é necessário identificar a unidade linguística mais coerente com a análise. Em línguas ocidentais, as palavras podem ser usadas; em linguas como japones e chines, ideogramas ou caracteres são melhores; em línguas semíticas, poderíamos usar os radicais como tokens ou separar por unidades mínimas de sentido (desconhecido -> des, conhec, ido), dentro da classificação morfológica, para tokenizar, posto que por ser templática, o custo computacional de processar todas as palavras seria muito alto.
