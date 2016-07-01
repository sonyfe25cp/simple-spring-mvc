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


<bean id="freeMarker"
          class="org.springframework.web.servlet.view.freemarker.FreeMarkerViewResolver">
        <property name="cache" value="true"/>
        <property name="prefix" value=""/>
        <!-- 上面配置了加载路径，这边不用配置前缀了 -->
        <property name="suffix" value=".ftl"/>
        <property name="contentType" value="text/html;charset=UTF-8"/>
        <!-- 处理乱码 -->
    </bean>

    <!-- 页面View层基本信息设定 拦截所有视图请求，当找不到时报404，所以放后面 -->
    <bean id="viewResolver"
          class="org.springframework.web.servlet.view.InternalResourceViewResolver">
        <property name="viewClass" value="org.springframework.web.servlet.view.JstlView"/>
        <!-- 如果使用jstl的话，配置的属性 -->
        <property name="suffix" value=".jsp"/>
        <!-- 后缀 -->
        <property name="prefix" value="/WEB-INF/pages/"/>
        <!-- 前缀 -->
    </bean>

    <!-- Handler Mapping -->
    <bean class="org.springframework.web.servlet.mvc.annotation.DefaultAnnotationHandlerMapping"/>
















<context-param>
		<param-name>contextConfigLocation</param-name>
		<param-value>/WEB-INF/applicationContext.xml</param-value>
	</context-param>
	<listener>
		<listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
	</listener>

	<filter>
		<filter-name>characterEncodingFilter</filter-name>
		<filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
		<init-param>
			<param-name>encoding</param-name>
			<param-value>UTF-8</param-value>
		</init-param>
	</filter>
	<filter-mapping>
		<filter-name>characterEncodingFilter</filter-name>
		<url-pattern>/*</url-pattern>
	</filter-mapping>

	<servlet>
		<servlet-name>spring3</servlet-name>
		<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
		<load-on-startup>1</load-on-startup>
	</servlet>
	<servlet-mapping>
		<servlet-name>spring3</servlet-name>
		<url-pattern>/</url-pattern>
	</servlet-mapping>