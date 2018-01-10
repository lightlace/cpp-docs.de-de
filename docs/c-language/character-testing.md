---
title: Zeichentests | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aeea6573b49e3bb093c3eb343ac3c89c27f0466b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="character-testing"></a>Zeichentests
**ANSI 4.3.1** Die Zeichensätze, auf die die Funktionen `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint` und `isupper` prüfen  
  
 Die folgende Liste beschreibt diese Funktionen, wie sie vom Microsoft C-Compiler implementiert werden.  
  
|Funktion|Tests für|  
|--------------|---------------|  
|`isalnum`|Die Zeichen 0-9, A-Z, a-z ASCII 48-57, 65-90, 97-122|  
|`isalpha`|Die Zeichen A-Z, a-z ASCII 65-90, 97-122|  
|`iscntrl`|ASCII 0 –31, 127|  
|`islower`|Die Zeichen A–Z ASCII 97-122|  
|`isprint`|Die Zeichen A-Z, a-z, 0-9, Satzzeichen, Leerzeichen-ASCII 32-126|  
|`isupper`|Die Zeichen A–Z ASCII 65-90|  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)