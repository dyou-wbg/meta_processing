Sampled from 50K rows of 11M merged file. 
1) Converted to lower case
2) ran for non-english item cleaning
3) dropped edge-case that are clearly not economic themed paper or none-paper articles

"""
df_english_titles=df
df_english_titles['title'] = df_english_titles['title'].str.lower()
df_english_titles = df_english_titles[~df_english_titles['title'].str.contains('و|д|я|š|ü|à|é|ś|ä|ú', regex=True)]
df_english_titles=df_english_titles[~df_english_titles['title'].str.lower().isin(["conclusion",
                                                                                  "poetry",
                                                                                  "introduction",
                                                                                  "front matter",
                                                                                  "editorial",
                                                                                  "back matter",
                                                                                  "correspondence",
                                                                                  "list of abbreviations",
                                                                                  "book Reviews",
                                                                                  "calendar of coming events",
                                                                                  "[notifiable diseases and mortality tables]",
                                                                                  "notifiable diseases and mortality tables"])]
"""
