# Captcha in BIGACE

The default captcha solution in BIGACE is B2evo. 

To change the Captcha implementation, you have to configure the class at Administration -> System -> Configurations - Package "**system**" - Key "**captcha**".

## B2evo Captcha (default)

Configuration:

	
	classes.util.captcha.B2EvoCaptcha


## Securimage

See [bigace:extensions:captcha:securimage](bigace/extensions/captcha/securimage).
