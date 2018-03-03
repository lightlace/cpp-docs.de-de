---
title: Breitzeichen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab885d5d807fe81b3058d533a70cdbaa9e3e523a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wide-characters"></a>Breitzeichen
**ANSI 3.1.3.4** Der Wert einer ganzzahligen Zeichenkonstante, die mehr als ein Zeichen enthält, oder der Breitzeichenkonstante, die mehr als ein Multibytezeichen enthält  
  
 Die reguläre Zeichenkonstante "ab" verfügt über den Ganzzahlwert (int)0x6162. Wenn es mehr als ein Byte gibt, werden die zuvor gelesenen Bytes durch den Wert von **CHAR_BIT** nach links verschoben, und das nächste Byte wird unter Verwendung des bitweisen OR-Operators mit den niedrigsten **CHAR_BIT**-Bits verglichen. Die Anzahl von Bytes in der Mehrbytezeichenkonstante kann "sizeof(int)" nicht überschreiten, was für den 32-Bit-Zielcode 4 bedeutet.  
  
 Die Mehrbytezeichenkonstante wird wie oben gelesen und mithilfe der `mbtowc`-Laufzeitfunktion zu einer Breitzeichenkonstante konvertiert. Wenn sich daraus keine gültige Mehrbytezeichenkonstante ergibt, wird ein Fehler ausgegeben. In jeden Fall wird die von der `mbtowc`-Funktion überprüfte Anzahl von Bytes auf den Wert von `MB_CUR_MAX` beschränkt.  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichen](../c-language/characters.md)