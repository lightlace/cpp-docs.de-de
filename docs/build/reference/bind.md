---
title: "/BIND"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/bind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/BIND-editbin-Option"
  - "BIND-editbin-Option"
  - "-BIND-editbin-Option"
  - "Einstiegspunkte"
  - "Einstiegspunkte, Adressen"
  - "Importieren einer Adressentabelle"
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /BIND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/BIND[:PATH=path]  
```  
  
## Hinweise  
 Durch diese Option werden die Adressen der Einstiegspunkte festgelegt, die sich in der Importadressentabelle für eine ausführbare Datei oder DLL befinden.  Mithilfe dieser Option können Sie die Ladezeit eines Programms reduzieren.  
  
 Geben Sie die ausführbare Datei und die DLLs des Programms im *files*\-Argument in der EDITBIN\-Befehlszeile an.  Mit dem optionalen *path*\-Argument für **\/BIND** geben Sie den Speicherort der DLLs an, die von den angegebenen Dateien verwendet werden.  Trennen Sie mehrere Verzeichnisse durch ein Semikolon \(**;**\).  Wenn für *path* kein Wert angegeben ist, durchsucht EDITBIN die in der **PATH**\-Umgebungsvariablen angegebenen Verzeichnisse.  Wurde für *path* ein Wert angegeben, ignoriert EDITBIN die **PATH**\-Umgebungsvariable.  
  
 Das Ladeprogramm legt die Adressen der Einstiegspunkte standardmäßig beim Laden eines Programms fest.  Wie lang dieser Prozess dauert, hängt von der Anzahl der DLLs und der Einstiegspunkte ab, auf die im Programm verwiesen wird.  Wenn ein Programm mit **\/BIND** geändert wurde und die Basisadressen für die ausführbare Datei und die DLLs nicht in Konflikt mit bereits geladenen DLLs stehen, braucht das Betriebssystem diese Adressen nicht festzulegen.  In einer Situation, in der den Dateien falsche Basisadressen zugewiesen wurden, verschiebt das Betriebssystem die DLLs des Programms und berechnet die Einstiegspunktadressen neu, wodurch allerdings die Ladezeit des Programms verlängert wird.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)