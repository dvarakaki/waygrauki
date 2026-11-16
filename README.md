# Waygrauki

Quiz de treino de **CI/CD** e **Kubernetes** para estudar para a prova, no estilo das salas de quiz ao vivo: pergunta na tela, quatro blocos coloridos, cronômetro e ranking.

**Jogar:** https://dvarakaki.github.io/waygrauki/

## O que tem

- **64 perguntas**: 27 de CI/CD e 37 de Kubernetes, todas com explicação.
- **Opções da partida**: assunto (misturado, só CI/CD ou só Kubernetes), número de perguntas (10, 20, 30 ou todas) e tempo por pergunta (20, 30, 45 s ou sem tempo).
- **Pontuação por velocidade**: de 500 a 1000 pontos por acerto, conforme o tempo que sobrou, mais um bônus de +100 por acerto seguido (até +500).
- **Power-ups**, um de cada por partida: **50/50** (elimina duas erradas), **+10 s** e **2x** (pontos em dobro).
- **Ranking** contra 4 bots que também pontuam a cada pergunta.
- **Resultado** com precisão por assunto, melhor sequência, tempo médio e revisão de todas as perguntas erradas.
- **Refazer só as erradas**, para fixar o que faltou.
- **Atalhos**: teclas `1` a `4` respondem e `Enter` vai para a próxima.
- **Quatro temas** no visual do portal Tech 2D: Padrão, Rosa claro, Roxo claro e Escuro (o Escuro é o padrão quando o sistema está no modo escuro).
- O recorde, o tema e as últimas opções ficam salvos no navegador.

## Assuntos cobertos

**CI/CD:** integração contínua, Continuous Delivery vs Deployment, GitHub Actions (`on`, `runs-on`, `needs`), GitLab CI, Jenkinsfile, artefatos e runners, pirâmide de testes, shift-left, trunk-based development, feature flags, blue-green, canary e rolling update, secrets, cache, SAST, métricas DORA, GitOps, IaC e registries.

**Kubernetes:** Pod, Deployment, ReplicaSet, Service (ClusterIP, NodePort), selectors e labels, Ingress, ConfigMap e Secret, namespaces, componentes do control plane (kube-apiserver, etcd, kube-scheduler) e dos nós (kubelet, kube-proxy), StatefulSet, DaemonSet, CronJob, PVC, liveness e readiness probes, HPA, `requests` e `limits`, erros comuns (`CrashLoopBackOff`, `ImagePullBackOff`, `OOMKilled`), Helm e comandos `kubectl`.

## Rodar localmente

É um único arquivo HTML, sem build e sem dependências. Basta abrir o `index.html` no navegador.

## Adicionar perguntas

As perguntas ficam no array `Q` dentro do `<script>` do `index.html`:

```js
{t:'k8s', q:'Enunciado da pergunta?',
 o:['Resposta certa', 'Errada 1', 'Errada 2', 'Errada 3'],
 e:'Explicação mostrada depois da resposta.'}
```

- `t`: assunto, `ci` ou `k8s`.
- `o`: a primeira opção é a correta (as opções são embaralhadas no jogo). Escreva as erradas com tamanho parecido com a certa e use confusões reais (ex.: canary × blue-green), para a resposta não se entregar pelo tamanho.
- Para verdadeiro ou falso, use `tf:true`, `o:['Verdadeiro','Falso']` e `a` com o índice da correta.
- Texto entre crases vira código, ex.: `` `kubectl get pods` ``.

## Licença

[MIT](LICENSE)
