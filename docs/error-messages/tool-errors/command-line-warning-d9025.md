---
title: "Befehlszeilenwarnung D9025"
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
  - "D9025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9025"
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Befehlszeilenwarnung D9025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überschreiben von 'Option1' mit 'Option2'  
  
 Die *Option1*\-Option wurde angegeben, aber durch *Option2* überschrieben.  Die *Option2*\-Option wurde verwendet.  
  
 Wenn zwei Optionen widersprüchliche oder inkompatible Direktiven angeben, wird die Direktive verwendet, die am weitesten rechts in der Befehlszeile angegeben oder impliziert wird.  
  
 Wenn Sie beim Kompilieren aus der Entwicklungsumgebung diese Warnung erhalten und nicht sicher sind, woher die miteinander in Konflikt stehenden Optionen stammen, überprüfen Sie Folgendes:  
  
-   Eine Option kann entweder im Code oder in den Projekteinstellungen des Projekts angegeben werden.  Wenn auf den [Eigenschaftenseiten der Befehlszeile](../../ide/command-line-property-pages.md) die miteinander in Konflikt stehenden Optionen im Feld **Alle Optionen** angezeigt werden, sind die Optionen auf den Eigenschaftenseiten des Projekts angegeben, andernfalls im Quellcode.  
  
     Wenn die Optionen auf den Eigenschaftenseiten des Projekts festgelegt sind, sehen Sie auf der Eigenschaftenseite des Compiler\-Präprozessors nach \(wobei der Projektknoten im Projektmappen\-Explorer ausgewählt ist\).  Wenn dort die festgelegte Option nicht angezeigt wird, überprüfen Sie die Einstellungen der Präprozessor\-Eigenschaftenseite für alle Quellcodedateien \(im Projektmappen\-Explorer\), um sicherzustellen, dass sie nicht dort hinzugefügt wurde.  
  
     Wenn die Optionen im Code festgelegt wurden, kann dies entweder im Code oder in den Windows\-Headern geschehen sein.  Sie können versuchen, eine vorverarbeitete Datei \([\/P](../../build/reference/p-preprocess-to-a-file.md)\) zu erstellen und diese nach dem Symbol zu durchsuchen.