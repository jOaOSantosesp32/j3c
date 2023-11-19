# j3c
esp32
  server.on("/", HTTP_GET, []() {
    String webpage = "<html><head><style>";
    webpage += "body {font-family: Arial, sans-serif; background-color: #e0e0e0; text-align: center;}";
    webpage += "h1 {font-size: 85px; margin: 20px 0;}";
    webpage += "h2 {font-size: 22px; margin: 10px 0;}";
    webpage += "a {font-size: 20px; text-decoration: none; display: block; margin: 10px auto; background-color: #f0f0f0; padding: 10px; border: 1px solid #c0c0c0; border-radius: 5px; color: #333;}";
    webpage += "a[href*='toggle/1'][style*='Ligado'] {background-color: green; color: white;}";
    webpage += "a[href*='toggle/2'][style*='Ligado'] {background-color: green; color: white;}";
    webpage += "a[href*='toggle/3'][style*='Ligado'] {background-color: green; color: white;}";
    webpage += "a[href*='toggle/4'][style*='Ligado'] {background-color: green; color: white;}";
    webpage += "</style></head><body>";
    webpage += "<h1>JC ClassroomCommand</h1>";
    webpage += "<p><a href='/toggle/1' style='font-size:5vw;text-decoration:none;'>LUZES - FRENTE - ";
    if (Estado_Do_Lamp_frente == LOW) {
      webpage += "Ligado";
    } else {
      webpage += "Desligado";
    }
    webpage += "</a></p>";
    webpage += "<p><a href='/toggle/2' style='font-size:5vw;text-decoration:none;'>LUZES - FUNDO - ";
    if (Estado_Do_Lamp_fundo == LOW) {
      webpage += "Ligado";
    } else {
      webpage += "Desligado";
    }
    webpage += "</a></p>";
    webpage += "<p><a href='/toggle/3' style='font-size:5vw;text-decoration:none;'>ABRIR - ";
    if (Estado_Do_Rsubir == LOW) {
      webpage += "Ligado";
    } else {
      webpage += "Desligado";
    }
    webpage += "</a></p>";
    webpage += "<p><a href='/toggle/4' style='font-size:5vw;text-decoration:none;'> FECHAR - ";
    if (Estado_Do_Rdescer == LOW) {
      webpage += "Ligado";
    } else {
      webpage += "Desligado";
    }
    webpage += "</a></p>";
    webpage += "</body></html>";
    server.send(200, "text/html", webpage);
  })
