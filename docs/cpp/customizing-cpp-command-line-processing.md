---
title: "Anpassen der C++-Befehlszeilenverarbeitung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_setenvp"
  - "_setargv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setargv-Funktion"
  - "_setenvp-Funktion"
  - "Befehlszeile, Verarbeiten"
  - "Befehlszeile, Verarbeiten von Argumenten"
  - "Befehlszeilenverarbeitung"
  - "Umgebung, Umgebungsverarbeitende Routine"
  - "Startcode, Anpassen der Befehlszeilenverarbeitung"
  - "Unterdrücken der Umgebungsverarbeitung"
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Anpassen der C++-Befehlszeilenverarbeitung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Wenn das Programm keine Befehlszeilenargumente akzeptiert, können Sie ein wenig Platz sparen, indem Sie die Verwendung der Bibliotheksroutine unterdrücken, die die Befehlszeilenverarbeitung ausführt.  Diese Routine wird **\_setargv** genannt und in [Platzhaltererweiterung](../cpp/wildcard-expansion.md) beschrieben.  Um die Verwendung zu unterdrücken, definieren Sie eine Routine, die in der Datei mit der **main**\-Funktion keine Aktion ausführt, und benennen Sie sie **\_setargv**.  Der Aufruf von **\_setargv** wird dann durch Ihre Definition von **\_setargv** erfüllt, und die Bibliotheksversion wird nicht geladen.  
  
 Auch wenn Sie niemals auf die Umgebungstabelle vom `envp`\-Argument aus zugreifen, können Sie anstelle der umgebungsverarbeitenden Routine **\_setenvp** Ihre eigene leere Routine bereitstellen.  Wie bei der **\_setargv**\-Funktion muss **\_setenvp** als **extern "C"** deklariert werden.  
  
 Das Programm ruft möglicherweise die **spawn**\- oder `exec`\-Gruppe von Routinen in der C\-Laufzeitbibliothek auf.  Wenn dies der Fall ist, sollten Sie die umgebungsverarbeitende Routine nicht unterdrücken, da diese Routine verwendet wird, um eine Umgebung aus dem übergeordneten Prozess an den untergeordneten Prozess zu übergeben.  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)