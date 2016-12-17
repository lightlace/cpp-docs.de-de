---
title: "Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Buildereignisse [C++], Ausgabeformat"
  - "Buildschritte [C++], Ausgabeformat"
  - "Builds [C++], Buildereignisse"
  - "Builds [C++], Benutzerdefinierte Buildschritte"
  - "Benutzerdefinierte Buildschritte [C++], Ausgabeformat"
  - "Ereignisse [C++], Build"
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn die Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses richtig formatiert ist, hat der Benutzer folgende Vorteile:  
  
-   Warnungen und Fehler werden im **Ausgabefenster** gezählt.  
  
-   Die Ausgabe wird im Fenster **Aufgabenliste** angezeigt.  
  
-   Wenn im **Ausgabefenster** auf die Ausgabe geklickt wird, wird das entsprechende Thema angezeigt.  
  
-   F1\-Operationen sind im Fenster **Aufgabenliste** oder im **Ausgabefenster** aktiviert.  
  
 Die Ausgabe sollte das folgende Format haben:  
  
 {*filename* \(*line\#* \[, *column\#*\]\) &#124; *toolname*} **:**  
  
 \[*any text*\] {**error** &#124; **warning**} *code\#\#\#\#***:** *localizable string*  
  
 \[ *any text* \]  
  
 Wobei:  
  
-   {*a* &#124; *b*} entweder von *a* oder von *b*.  
  
-   \[`ccc`\] ist eine optionale Zeichenfolge oder ein optionaler Parameter.  
  
 Beispiel:  
  
 C:\\*sourcefile.cpp*\(134\): C2143 Fehler: Syntaxfehler: Fehlt "; " vor "}"  
  
 LINK: schwer wiegender Fehler LNK1104: kann nicht geöffnet Datei '*somelib.lib*'  
  
## Siehe auch  
 [Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](../ide/understanding-custom-build-steps-and-build-events.md)