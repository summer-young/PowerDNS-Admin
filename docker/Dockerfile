发件人阿尔卑斯山：3.17AS公司建设者
ARG公司GOARCH=adm64
ARG公司BUILD_DEPENDENCIES= &#34;b条u个我我d日 -b条一秒e（电子） \
我我b条（f）（f）我 -d日e（电子）v（v） \
我我b条第页q个 -d日e（电子）v（v） \
我我b条x个米我2 -d日e（电子）v（v） \
米一第页我一d日b条 -c（c）o个n个n个e（电子）c（c）t吨o个第页 -c（c） -d日e（电子）v（v） \
o个第页e（电子）n个我d日一第页 -d日e（电子）v（v） \
第页年t吨小时o个n个3 -d日e（电子）v（v） \
x个米我秒e（电子）c（c） -d日e（电子）v（v） \
n个第页米 \
年一第页n个 \
c（c）一第页克o个 &#34;

ENV LC_ALL=en_US.UTF-8 \
LANG=en_US.UTF-8 \
LANGUAGE=en_US.UTF-8 \
FLASK_APP=/build/powerdnsadmin/__init__.py

#获取依赖项
#py3-pip不应属于BUILD_DEPENDENCIES。否则，当我们删除
#它们在构建阶段的末尾使用“apk-del”，python请求模块
#也将被删除-（用alpine:3.12和python 3.8.5测试）。
RUN（运行）apk add--无缓存${BUILD_DEPENDENCIES}&#38;&#38;\
apk add--无缓存py3-pip

 工作总监/建造

#我们首先复制requirements.txt以利用Docker缓存
副本./requirements.txt/build/requires.txt

#获取应用程序依赖项
RUN（运行）pip安装--升级pip&#38;&#38;\
pip安装--使用-pep517-r requirements.txt

#添加源
副本./内部版本

#准备资产
RUN（运行）纱线安装--pure-lockfile--生产&#38;&#38;\
纱线缓存清理\
sed-i-r-e &#34;秒 | &#39;第页c（c）秒秒米我n个 &#39; ,\秒 ? &#39;c（c）秒秒第页e（电子）w个第页我t吨e（电子） &#39; | &#39;第页c（c）秒秒米我n个 &#39; |克 &#34;/build/powerdnsadmin/assets.py&#38;&#38;\
烧瓶资产构建

RUN（运行）mv/build/powerdnsadmin/static/tmp/static&#38;&#38;\
mkdir/build/powerdnsadmin/static&#38;&#38;\
cp-r/tmp/static/generated/build/powerdnsadmin/static&#38;&#38;\
cp-r/tmp/static/assets/build/powerdnsadmin/static&#38;&#38;\
cp-r/tmp/static/img/build/powerdnsadmin/static&#38;&#38;\
查找/tmp/static/nodemodules-名称 &#39;w个e（电子）b条（f）o个n个t吨秒 &#39;-exec cp-r{}/build/powerdnsadmin/static\；&#38;&#38;\
查找/tmp/static/nodemodules-名称 &#39;（f）o个n个t吨秒 &#39;-exec cp-r{}/build/powerdnsadmin/static\；&#38;&#38;\
查找/tmp/static/nodemodules/icheck/skins/square-名称 &#39; * .第页n个克 &#39;-exec-cp{}/build/powerdnsadmin/static/generated\；

RUN（运行） { \
回声 &#34;（f）第页o个米（f）我一秒k个 _一秒秒e（电子）t吨秒我米第页o个第页t吨E类n个v（v）我第页o个n个米e（电子）n个t吨 &#34; ; \
回声 &#34;一秒秒e（电子）t吨秒=E类n个v（v）我第页o个n个米e（电子）n个t吨 ( ) &#34; ; \
回声 &#34;一秒秒e（电子）t吨秒 .第页e（电子）克我秒t吨e（电子）第页 ( &#39;j个秒 _我o个克我n个 &#39; , &#39;克e（电子）n个e（电子）第页一t吨e（电子）d日 /我o个克我n个 .j个秒 &#39; ) &#34; ; \
回声 &#34;一秒秒e（电子）t吨秒 .第页e（电子）克我秒t吨e（电子）第页 ( &#39;j个秒 _v（v）一我我d日一t吨我o个n个 &#39; , &#39;克e（电子）n个e（电子）第页一t吨e（电子）d日 /v（v）一我我d日一t吨我o个n个 .j个秒 &#39; ) &#34; ; \
回声 &#34;一秒秒e（电子）t吨秒 .第页e（电子）克我秒t吨e（电子）第页 ( &#39;c（c）秒秒 _我o个克我n个 &#39; , &#39;克e（电子）n个e（电子）第页一t吨e（电子）d日 /我o个克我n个 .c（c）秒秒 &#39; ) &#34; ; \
回声 &#34;一秒秒e（电子）t吨秒 .第页e（电子）克我秒t吨e（电子）第页 ( &#39;j个秒 _米一我n个 &#39; , &#39;克e（电子）n个e（电子）第页一t吨e（电子）d日 /米一我n个 .j个秒 &#39; ) &#34; ; \
回声 &#34;一秒秒e（电子）t吨秒 .第页e（电子）克我秒t吨e（电子）第页 ( &#39;c（c）秒秒 _米一我n个 &#39; , &#39;克e（电子）n个e（电子）第页一t吨e（电子）d日 /米一我n个 .c（c）秒秒 &#39; ) &#34; ; \
}&#62;/build/powerdnsadmin/assets.py

#移动应用程序
RUN mkdir -p /app && \
    cp -r /build/migrations/ /build/powerdnsadmin/ /build/run.py /app && \
    mkdir -p /app/configs && \
    cp -r /build/configs/docker_config.py /app/configs

# Build image
FROM alpine:3.17

ENV FLASK_APP=/app/powerdnsadmin/__init__.py \
    USER=pda

RUN apk add --no-cache mariadb-connector-c postgresql-client py3-gunicorn py3-pyldap py3-flask py3-psycopg2 xmlsec tzdata libcap && \
    addgroup -S ${USER} && \
    adduser -S -D -G ${USER} ${USER} && \
    mkdir /data && \
    chown ${USER}:${USER} /data && \
    setcap cap_net_bind_service=+ep $(readlink -f /usr/bin/python3) && \
    apk del libcap

COPY --from=builder /usr/bin/flask /usr/bin/
COPY --from=builder /usr/lib/python3.10/site-packages /usr/lib/python3.10/site-packages/
COPY --from=builder --chown=root:${USER} /app /app/
COPY ./docker/entrypoint.sh /usr/bin/

WORKDIR /app
RUN chown ${USER}:${USER} ./configs /app && \
    cat ./powerdnsadmin/default_config.py ./configs/docker_config.py > ./powerdnsadmin/docker_config.py

EXPOSE 80/tcp
USER ${USER}
HEALTHCHECK CMD ["wget","--output-document=-","--quiet","--tries=1","http://127.0.0.1/"]
ENTRYPOINT ["entrypoint.sh"]
CMD ["gunicorn","powerdnsadmin:create_app()"]
