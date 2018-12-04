# spring-io-initializr-0.6.0.RELEASE

initializr-service 编译失败原因是 pom文件错误

pom文件中修改内容为 

	1 
		<parent>
		<groupId>io.spring.initializr</groupId>
		<artifactId>initializr</artifactId>
		<version>0.6.0.RELEASE</version>
		</parent>
	2 
		<build>
		<finalName>initializr-service</finalName>
		<plugins>
			<plugin>
				<groupId>pl.project13.maven</groupId>
				<artifactId>git-commit-id-plugin</artifactId>
				<version>2.2.3</version>
				<!--<executions>
					<execution>
						<goals>
							<goal>revision</goal>
						</goals>
					</execution>
				</executions>-->
				<configuration>
					<!--<dotGitDirectory>${project.basedir}/../.git</dotGitDirectory>-->
					<dateFormat>yyyy-MM-dd'T'HH:mm:ssZ</dateFormat>
					<generateGitPropertiesFile>true</generateGitPropertiesFile>
					<generateGitPropertiesFilename>
						${project.build.outputDirectory}/git.properties
					</generateGitPropertiesFilename>
				</configuration>
				</plugin>
