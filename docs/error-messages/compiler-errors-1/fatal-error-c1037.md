---
title: "Schwerwiegender Fehler C1037"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C1037"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1037"
ms.assetid: 79103bca-ccfb-42e7-aef9-9b90c15b162f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1037
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Objektdatei kann nicht geöffnet werden  
  
 Die durch [\/Fo](../../build/reference/fo-object-file-name.md) angegebene Objektdatei kann nicht geöffnet werden.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Ungültiger Dateiname.  
  
2.  Es ist nicht genügend Speicher verfügbar, um die Datei zu öffnen.  
  
3.  Die Datei wird von einem anderen Prozess verwendet.  
  
4.  Eine schreibgeschützte Datei hat den gleichen Namen.  
  
 In Visual C\+\+ .NET \(Version 1300 des Compilers\) liegt ein Fehler vor, der erfordert, dass das Benutzergebietsschema richtig festgelegt wird, wenn der Dateiname \(oder der Verzeichnispfad zum Dateinamen\) MBCS\-Zeichen enthält. Das Festlegen des Systemgebietsschemas ist nicht ausreichend; das Benutzergebietsschema muss festgelegt werden, damit MBCS\-Zeichen verarbeitet werden.