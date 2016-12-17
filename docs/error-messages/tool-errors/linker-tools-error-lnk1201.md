---
title: "Linkertoolfehler LNK1201"
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
  - "LNK1201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1201"
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler beim Schreiben in die Programmdatenbank 'Dateiname'. Möglicherweise ist nicht genügend Festplattenspeicher verfügbar, ist der Pfad ungültig oder reichen die Zugriffsrechte nicht aus  
  
 Durch LINK konnte nicht in die Programmdatenbank \(PDB\) für die Ausgabedatei geschrieben werden.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Datei ist beschädigt.  Löschen Sie die PDB\-Datei, und stellen Sie eine neue Verknüpfung her.  
  
2.  Es war nicht genügend Speicherplatz zum Schreiben in die Datei verfügbar.  
  
3.  Das Laufwerk ist möglicherweise aufgrund eines Netzwerkproblems nicht verfügbar.  
  
4.  Der Debugger wurde für das Programm, das verknüpft werden soll, aktiviert.  
  
5.  Kein weiterer Heap\-Speicher verfügbar.  Weitere Informationen finden Sie unter [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md).