# Chapter 1 - Web hooks

Web hooks are a fun way to dynamically add behavior to web services, without having to go to the web service for support.

```groovy
import org.springframework.context.annotation.Bean

import com.github.shredder121.gh_event_api.GHEventApiServer
import com.github.shredder121.gh_event_api.handler.status.StatusHandler

class Application {

	@Bean
	StatusHandler statusHandler() {
		def bean = { payload ->
			println payload.description
		}
	}
}

GHEventApiServer.start Application
```

This is an example of a minimal server.
