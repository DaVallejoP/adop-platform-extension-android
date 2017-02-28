FROM accenture/adop-jenkins-slave:0.1.4
# Download and untar SDK 
RUN yum -y install tar curl   
ENV ANDROID_SDK_URL https://dl.google.com/android/android-sdk_r24.4.1-linux.tgz
RUN curl -L "${ANDROID_SDK_URL}" | tar --no-same-owner -xz -C /usr/local
ENV ANDROID_HOME /usr/local/android-sdk-linux 
ENV ANDROID_SDK /usr/local/android-sdk-linux 
ENV PATH ${ANDROID_HOME}/tools:$ANDROID_HOME/platform-tools:$PATH 
# Install Android SDK components 
ENV ANDROID_SDK_COMPONENTS "platform-tools,build-tools-25.0.2,android-25,extra-android-m2repository,extra-google-m2repository" 
RUN echo y | android update sdk --no-ui --all --filter "$ANDROID_SDK_COMPONENTS"
# Support Gradle 
ENV TERM dumb
ENV JAVA_OPTS -Xms256m -Xmx1536M