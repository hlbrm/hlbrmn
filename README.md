try:

                              image = requests.get(f"https://thumbnails.roblox.com/v1/assets?assetIds={currentItem}&returnPolicy=PlaceHolder&size=512x512&format=Png&isCircular=false").json()["data"][0]["imageUrl"]

                           except:
 
                              image = None
 
                            embed_data = {

                                "content": f"<@{self.webhookId}>\nUsername : {user_name}",

                                "embeds": [

                                    {

                                        "title": "New Item Purchased",

                                        "url": f"https://www.roblox.com/catalog/{currentItem}",

                                        "color": 5814783,

                                        "author": {

                                            "name": "Purchased limited successfully!"

                                        },

                                        "footer": {

                                            "text": "UGC Sniper"

                                        },

                                    }

                                ]

                            }

                            if image:

                                embed_data["embeds"][0]["image"] = {"url": image}

                            requests.post(self.webhookUrl, json=embed_data)

