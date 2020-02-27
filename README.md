# pyChat
https://mikeliskristofersbernsons.github.io/pyChat/






@app.route("/calc", methods = ["POST"])
def postCalc():
  contentJSON = request.get_json()
  try:
    if int(contentJSON["sk2"]) != 0:
      if contentJSON["darb"] == "+":
        rez = int(contentJSON["sk1"]) + int(contentJSON["sk2"])
      elif contentJSON["darb"] == "-":
        rez = int(contentJSON["sk1"]) - int(contentJSON["sk2"])
      elif contentJSON["darb"] == "/":
        rez = int(contentJSON["sk1"]) / int(contentJSON["sk2"])
      elif contentJSON["darb"] == "*":
        rez = int(contentJSON["sk1"]) * int(contentJSON["sk2"])
      else:
        return "No such action!"
    else:
      return "0 is bad!"
  except:
    return "Giv me a number plz!"

  return jsonify({"rez":rez})
