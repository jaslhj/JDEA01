#API learning

import requests

def translate(text, source="en", target="es"):
    """Translate text using the MyMemory API and return the translated string."""
    response = requests.get(
        "https://api.mymemory.translated.net/get",
        params={"q": text, "langpair": f"{source}|{target}"},
        timeout=10,
    )
    return response.json()["responseData"]["translatedText"]

print(translate("Hello world!"))                 # English -> Spanish (default)
print(translate("Good morning", "en", "fr"))     # English -> French



import requests

API_KEY = ""   # paste your Cat API key here

#https://docs.thecatapi.com/docs/examples/breeds
headers = {"x-api-key": API_KEY}
response = requests.get(
    "https://api.thecatapi.com/v1/breeds/search",
    params={"q": "abys"},
    headers=headers,
    timeout=10,
)
print(response.status_code)
print(response.json())