
1. Abaixo, exemplo de um tweet contido no arquivo data/collect_foradilma-20151216.txt

[on_data] {"created_at":"Wed Dec 16 21:59:58 +0000 2015","id":677246816526667776,"id_str":"677246816526667776","text":"Eles n\u00e3o est\u00e3o interessados no Brasil\nA prova, \u00e9 s\u00f3 olha a bandeira que essa manifesta\u00e7\u00e3o leva no peito.\n#ForaDilma  https:\/\/t.co\/jm0yEu91ov","source":"\u003ca href=\"http:\/\/twitter.com\/download\/android\" rel=\"nofollow\"\u003eTwitter for Android\u003c\/a\u003e","truncated":false,"in_reply_to_status_id":null,"in_reply_to_status_id_str":null,"in_reply_to_user_id":null,"in_reply_to_user_id_str":null,"in_reply_to_screen_name":null,"user":{"id":91837810,"id_str":"91837810","name":"Andr\u00e9 Luiz Andrade","screen_name":"Andrezinhostar","location":"Aracaju","url":"http:\/\/www.soundcloud.com\/andrezinhoandrade","description":"Musico, compositor da nova gera\u00e7\u00e3o!","protected":false,"verified":false,"followers_count":201,"friends_count":283,"listed_count":2,"favourites_count":10,"statuses_count":2685,"created_at":"Sun Nov 22 18:14:40 +0000 2009","utc_offset":0,"time_zone":"London","geo_enabled":false,"lang":"pt","contributors_enabled":false,"is_translator":false,"profile_background_color":"8B542B","profile_background_image_url":"http:\/\/pbs.twimg.com\/profile_background_images\/254599853\/free_twitter_designer.jpg","profile_background_image_url_https":"https:\/\/pbs.twimg.com\/profile_background_images\/254599853\/free_twitter_designer.jpg","profile_background_tile":false,"profile_link_color":"9D582E","profile_sidebar_border_color":"D9B17E","profile_sidebar_fill_color":"EADEAA","profile_text_color":"333333","profile_use_background_image":true,"profile_image_url":"http:\/\/pbs.twimg.com\/profile_images\/608449528568672256\/20C4us-r_normal.jpg","profile_image_url_https":"https:\/\/pbs.twimg.com\/profile_images\/608449528568672256\/20C4us-r_normal.jpg","profile_banner_url":"https:\/\/pbs.twimg.com\/profile_banners\/91837810\/1410290898","default_profile":false,"default_profile_image":false,"following":null,"follow_request_sent":null,"notifications":null},"geo":null,"coordinates":null,"place":null,"contributors":null,"quoted_status_id":677229908473610240,"quoted_status_id_str":"677229908473610240","quoted_status":{"created_at":"Wed Dec 16 20:52:47 +0000 2015","id":677229908473610240,"id_str":"677229908473610240","text":"Movimentos sociais comprados pelo governo, levam suas tropas para apoiar Dilma . S\u00f3 n\u00e3o combinaram com o povo kkkkk muito kkkkk","source":"\u003ca href=\"http:\/\/twitter.com\/#!\/download\/ipad\" rel=\"nofollow\"\u003eTwitter for iPad\u003c\/a\u003e","truncated":false,"in_reply_to_status_id":null,"in_reply_to_status_id_str":null,"in_reply_to_user_id":null,"in_reply_to_user_id_str":null,"in_reply_to_screen_name":null,"user":{"id":126436384,"id_str":"126436384","name":"Silas Malafaia","screen_name":"PastorMalafaia","location":"Rio de Janeiro","url":"http:\/\/www.vitoriaemcristo.org","description":"Twitter oficial do pastor e presidente da Assembleia de Deus Vit\u00f3ria em Cristo e apresentador do programa Vit\u00f3ria em Cristo","protected":false,"verified":true,"followers_count":1135648,"friends_count":69,"listed_count":3171,"favourites_count":60,"statuses_count":24225,"created_at":"Thu Mar 25 21:45:59 +0000 2010","utc_offset":-7200,"time_zone":"Brasilia","geo_enabled":false,"lang":"pt","contributors_enabled":false,"is_translator":false,"profile_background_color":"FFFFFF","profile_background_image_url":"http:\/\/pbs.twimg.com\/profile_background_images\/89644064\/fd_silasmalafaia_copy.jpg","profile_background_image_url_https":"https:\/\/pbs.twimg.com\/profile_background_images\/89644064\/fd_silasmalafaia_copy.jpg","profile_background_tile":false,"profile_link_color":"CC6731","profile_sidebar_border_color":"780C0C","profile_sidebar_fill_color":"F5DEBA","profile_text_color":"780C0C","profile_use_background_image":true,"profile_image_url":"http:\/\/pbs.twimg.com\/profile_images\/623504625430339584\/afKvM48O_normal.jpg","profile_image_url_https":"https:\/\/pbs.twimg.com\/profile_images\/623504625430339584\/afKvM48O_normal.jpg","profile_banner_url":"https:\/\/pbs.twimg.com\/profile_banners\/126436384\/1440760410","default_profile":false,"default_profile_image":false,"following":null,"follow_request_sent":null,"notifications":null},"geo":null,"coordinates":null,"place":null,"contributors":null,"is_quote_status":false,"retweet_count":0,"favorite_count":0,"entities":{"hashtags":[],"urls":[],"user_mentions":[],"symbols":[]},"favorited":false,"retweeted":false,"filter_level":"low","lang":"pt"},"is_quote_status":true,"retweet_count":0,"favorite_count":0,"entities":{"hashtags":[{"text":"ForaDilma","indices":[105,115]}],"urls":[{"url":"https:\/\/t.co\/jm0yEu91ov","expanded_url":"https:\/\/twitter.com\/PastorMalafaia\/status\/677229908473610240","display_url":"twitter.com\/PastorMalafaia\u2026","indices":[117,140]}],"user_mentions":[],"symbols":[]},"favorited":false,"retweeted":false,"possibly_sensitive":false,"filter_level":"low","lang":"pt","timestamp_ms":"1450303198354"}


Como usar o BASH (terminal do Mac) gerar um CSV a partir dos arquivos coletados:

grep on_data collect_foradilma-20151216.txt | sed 's/^.*{\"created_at\":\".*\",\"id\":\([0-9]*\),\"id_str\":\".*\",\"text\":\(.*\),\"source\".*\"user\":{\"id\":[0-9]*,\"id_str\":\"[0-9]*\",\"name\":\".*\",\"screen_name\":\(.*\),\"location\".*/\1,\2,\3/' | head -1