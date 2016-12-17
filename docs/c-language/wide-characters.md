---
title: "Breitzeichen"
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
  - "C"
helpviewer_keywords: 
  - "Breitzeichen"
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Breitzeichen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.1.3.4** Der Wert einer ganzzahligen Zeichenkonstante, die mehr als ein Zeichen enthält, oder der Breitzeichenkonstante, die mehr als ein Mehrbytezeichen enthält  
  
 Die reguläre Zeichenkonstante "ab" verfügt über den Ganzzahlwert \(int\)0x6162.  Wenn mehr als ein Byte gibt, werden die zuvor gelesenen Bytes durch den Wert von **CHAR\_BIT** nach links verschoben und das nächste Byte wird unter Verwendung des bitweisen OR\-Operators mit den niedrigsten **CHAR\_BIT**\-Bits verglichen.  Die Anzahl von Bytes in der Mehrbytezeichenkonstante kann "sizeof\(int\)" nicht überschreiten, was für den 32\-Bit\-Zielcode 4 bedeutet.  
  
 Die Mehrbytezeichenkonstante wird wie oben gelesen und mithilfe der `mbtowc`\-Laufzeitfunktion zu einer Breitzeichenkonstante konvertiert.  Wenn sich daraus keine gültige Mehrbytezeichenkonstante ergibt, wird ein Fehler ausgegeben.  In jeden Fall wird die von der `mbtowc`\-Funktion überprüfte Anzahl von Bytes auf den Wert von `MB_CUR_MAX` beschränkt.  
  
## Siehe auch  
 [Zeichen](../c-language/characters.md)