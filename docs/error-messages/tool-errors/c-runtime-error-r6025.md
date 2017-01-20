---
title: "C-Laufzeitfehler R6025"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "R6025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6025"
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# C-Laufzeitfehler R6025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rein virtueller Funktionsaufruf  
  
 Es wurde kein Objekt als Instanz definiert, um den Aufruf der rein virtuellen Funktion zu behandeln.  
  
 Wenn dieser Fehler angezeigt wird, wenden Sie sich an den technischen Support für Ihre Anwendung.  
  
 Dieser Fehler wurde durch das Aufrufen einer virtuellen Funktion in einer abstrakten Basisklasse durch einen Zeiger verursacht, der durch eine Umwandlung in den Typ der abgeleiteten Klasse erstellt wurde, jedoch tatsächlich einen Zeiger auf die Basisklasse darstellt.  Dies kann auftreten, wenn ein **void\***\-Zeiger, der beim Erstellen der Basisklasse erstellt wurde, in einen Zeiger auf eine Klasse umgewandelt wird.  
  
 Weitere Informationen finden Sie auf der Website [Microsoft unterstützt](http://go.microsoft.com/fwlink/?LinkId=75220).