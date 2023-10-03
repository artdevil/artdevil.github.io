---
layout: post
title: 'How to fix bug OpenSSL in gemfile'
date: '2023-10-03 13:25:00 0000'
categories: ['ruby', 'ruby on rails']
---

![https://www.ldttechnology.com/services/mobile-app-web-development](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*ttn5uU2KBE6aFxYCbND7yQ.jpeg "OpenSSL")


```bash
Building native extensions. This could take a while...
ERROR:  Error installing openssl:
 ERROR: Failed to build gem native extension.

    current directory: /Users/adhigunasabril/.rvm/gems/ruby-3.2.2/gems/openssl-3.2.0/ext/openssl
/Users/adhigunasabril/.rvm/rubies/ruby-3.2.2/bin/ruby extconf.rb
checking for rb_io_descriptor()... yes
checking for rb_io_maybe_wait(0, Qnil, Qnil, Qnil) in ruby/io.h... yes
checking for t_open() in -lnsl... no
checking for socket() in -lsocket... no
checking for openssl/ssl.h... yes
checking for LIBRESSL_VERSION_NUMBER in openssl/opensslv.h... no
checking for OpenSSL version >= 1.0.2... yes
checking for RAND_egd() in openssl/rand.h... no
checking for ENGINE_load_dynamic() in openssl/engine.h... yes
checking for ENGINE_load_4758cca() in openssl/engine.h... no
checking for ENGINE_load_aep() in openssl/engine.h... no
checking for ENGINE_load_atalla() in openssl/engine.h... no
checking for ENGINE_load_chil() in openssl/engine.h... no
checking for ENGINE_load_cswift() in openssl/engine.h... no
checking for ENGINE_load_nuron() in openssl/engine.h... no
checking for ENGINE_load_sureware() in openssl/engine.h... no
checking for ENGINE_load_ubsec() in openssl/engine.h... no
checking for ENGINE_load_padlock() in openssl/engine.h... no
checking for ENGINE_load_capi() in openssl/engine.h... no
checking for ENGINE_load_gmp() in openssl/engine.h... no
checking for ENGINE_load_gost() in openssl/engine.h... no
checking for ENGINE_load_cryptodev() in openssl/engine.h... yes
checking for SSL.ctx in openssl/ssl.h... no
checking for EVP_MD_CTX_new() in openssl/evp.h... yes
checking for EVP_MD_CTX_free(NULL) in openssl/evp.h... yes
checking for EVP_MD_CTX_pkey_ctx(NULL) in openssl/evp.h... no
checking for X509_STORE_get_ex_data(NULL, 0) in openssl/x509.h... yes
checking for X509_STORE_set_ex_data(NULL, 0, NULL) in openssl/x509.h... yes
checking for X509_STORE_get_ex_new_index(0, NULL, NULL, NULL, NULL) in openssl/x509.h... yes
checking for X509_CRL_get0_signature(NULL, NULL, NULL) in openssl/x509.h... yes
checking for X509_REQ_get0_signature(NULL, NULL, NULL) in openssl/x509.h... yes
checking for X509_REVOKED_get0_serialNumber(NULL) in openssl/x509.h... yes
checking for X509_REVOKED_get0_revocationDate(NULL) in openssl/x509.h... yes
checking for X509_get0_tbs_sigalg(NULL) in openssl/x509.h... yes
checking for X509_STORE_CTX_get0_untrusted(NULL) in openssl/x509.h... yes
checking for X509_STORE_CTX_get0_cert(NULL) in openssl/x509.h... yes
checking for X509_STORE_CTX_get0_chain(NULL) in openssl/x509.h... yes
checking for OCSP_SINGLERESP_get0_id(NULL) in openssl/ocsp.h... yes
checking for SSL_CTX_get_ciphers(NULL) in openssl/ssl.h... yes
checking for X509_up_ref(NULL) in openssl/x509.h... yes
checking for X509_CRL_up_ref(NULL) in openssl/x509.h... yes
checking for X509_STORE_up_ref(NULL) in openssl/x509.h... yes
checking for SSL_SESSION_up_ref(NULL) in openssl/ssl.h... yes
checking for EVP_PKEY_up_ref(NULL) in openssl/evp.h... yes
checking for SSL_CTX_set_min_proto_version(NULL, 0) in openssl/ssl.h... yes
checking for SSL_CTX_get_security_level(NULL) in openssl/ssl.h... yes
checking for X509_get0_notBefore(NULL) in openssl/x509.h... yes
checking for SSL_SESSION_get_protocol_version(NULL) in openssl/ssl.h... yes
checking for TS_STATUS_INFO_get0_status(NULL) in openssl/ts.h... yes
checking for TS_STATUS_INFO_get0_text(NULL) in openssl/ts.h... yes
checking for TS_STATUS_INFO_get0_failure_info(NULL) in openssl/ts.h... yes
checking for TS_VERIFY_CTS_set_certs(NULL, NULL) in openssl/ts.h... no
checking for TS_VERIFY_CTX_set_store(NULL, NULL) in openssl/ts.h... yes
checking for TS_VERIFY_CTX_add_flags(NULL, 0) in openssl/ts.h... yes
checking for TS_RESP_CTX_set_time_cb(NULL, NULL, NULL) in openssl/ts.h... yes
checking for EVP_PBE_scrypt("", 0, (unsigned char *)"", 0, 0, 0, 0, 0, NULL, 0) in openssl/evp.h... yes
checking for SSL_CTX_set_post_handshake_auth(NULL, 0) in openssl/ssl.h... yes
checking for EVP_PKEY_check(NULL) in openssl/evp.h... yes
checking for EVP_PKEY_new_raw_private_key(0, NULL, (unsigned char *)"", 0) in openssl/evp.h... yes
checking for SSL_CTX_set_ciphersuites(NULL, "") in openssl/ssl.h... yes
checking for SSL_set0_tmp_dh_pkey(NULL, NULL) in openssl/ssl.h... no
checking for ERR_get_error_all(NULL, NULL, NULL, NULL, NULL) in openssl/err.h... no
checking for TS_VERIFY_CTX_set_certs(NULL, NULL) in openssl/ts.h... no
checking for SSL_CTX_load_verify_file(NULL, "") in openssl/ssl.h... no
checking for BN_check_prime(NULL, NULL, NULL) in openssl/bn.h... no
checking for EVP_MD_CTX_get0_md(NULL) in openssl/evp.h... no
checking for EVP_MD_CTX_get_pkey_ctx(NULL) in openssl/evp.h... no
checking for EVP_PKEY_eq(NULL, NULL) in openssl/evp.h... no
checking for EVP_PKEY_dup(NULL) in openssl/evp.h... no
creating extconf.h
creating Makefile
```

Some annoying errors happen in Ruby when faced with OpenSSL bug. With showing only C++ code make error there a few suggest how to fixed it.

But don’t panic. Take a deep breath and clear your mind. Based on my experiences there are a few steps how to identify and fix it.

1. **Take a look at your gemfile.lock** needed and checking the version of OpenSSL you want to install. Rails by default use your default OpenSSL in your system, but sometimes other gems need other versions. So make it clear to see what OpenSSL version.

```bash
extensions/arm64-darwin-22/3.2.0/openssl-3.2.0/gem_make.out
```

2. **Check in the system** if there is any OpenSSL library compatible with that version. If not you need to install it first. I’m using Mac with homebrew so it the easy to do just using

```bash
brew install openssl@3 # for example when the error showing openssl-3.2.0
```

3. **After successful installation** for the system install it using the option ‘ — with-openssl-dir’

```bash
gem install openssl -- --with-openssl-dir=/opt/homebrew/opt/openssl@3 # replace it with your openssl directory
```

hopefully, it can help!