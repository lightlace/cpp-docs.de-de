---
title: "NMAKE: Schwerwiegender Fehler U1045"
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
  - "U1045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1045"
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE: Schwerwiegender Fehler U1045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erzeugen eines Prozesses fehlgeschlagen: Meldung  
  
 Ein Programm oder Befehl mit Namen NMAKE ist aus dem angegebenen Grund fehlgeschlagen.  Wenn NMAKE ein anderes Programm aufruft, z. B. Compiler oder Linker – schlägt der Aufruf eventuell fehl oder ein Fehler wird vom aufgerufenen Programm zurückgegeben.  Diese Meldung wird verwendet, um den Fehler zu melden.  
  
 Um dieses Problem zu beheben, müssen Sie zunächst die Ursache des Fehlers bestimmen.  Sie können die Befehle von der NMAKE gemeldeten [\/N](../../build/nmake-options.md)\-Option verwenden, um die Umgebungseinstellungen zu überprüfen und die von NMAKE in der Befehlszeile ausgeführten Aktionen zu wiederholen.