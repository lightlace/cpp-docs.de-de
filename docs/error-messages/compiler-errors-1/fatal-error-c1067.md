---
title: "Schwerwiegender Fehler C1067"
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
  - "C1067"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1067"
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1067
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit: Die Größenbeschränkung von 64 KB für Typeneinträge wurde überschritten  
  
 Dieser Fehler tritt z. B. auf, wenn ein Symbol über einen ergänzten Namen mit mehr als 247 Zeichen verfügt.  Verkürzen Sie den Symbolnamen, um das Problem zu beheben.  
  
 Bei der Erstellung von Debuginformationen durch den Compiler werden Typeneinträge ausgegeben, um im Quellcode gefundene Typen zu definieren.  Typeneinträge enthalten beispielsweise einfache Strukturen und Argumentlisten von Funktionen.  Einige dieser Typeneinträge können große Listen sein.  
  
 Typeneinträge dürfen eine Größe von je 64 KB nicht überschreiten.  Wird diese 64 KB\-Grenze überschritten, wird die oben stehende Fehlermeldung angezeigt.  
  
 C1067 wird möglicherweise auch ausgegeben, wenn viele Symbole mit langen Namen vorhanden sind oder wenn eine Klasse, Struktur oder Union über zu viele Member verfügt.