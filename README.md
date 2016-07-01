simple-spring-mvc
=================

a simple spring mvc demo for quickly build a j2ee web application

Notice:

if(maven is ok for you){
  then please use the master branch
}else{
  use the not-maven branch
}


<bean id="freemarkerConfig"
          class="org.springframework.web.servlet.view.freemarker.FreeMarkerConfigurer">
        <property name="templateLoaderPath" value="/WEB-INF/ftl/"/>
        <!--配置 模板加载路径 -->
        <property name="defaultEncoding" value="UTF-8"/>
        <property name="freemarkerSettings">
            <props>
                <prop key="template_update_delay">0</prop>
                <prop key="locale">zh_CN</prop>
                <prop key="datetime_format">yyyy-MM-dd HH:mm:ss</prop>
                <prop key="date_format">yyyy-MM-dd</prop>
                <prop key="number_format">#.##</prop>
                <prop key="auto_import">spring.ftl as spring</prop>
            </props>
        </property>
    </bean>