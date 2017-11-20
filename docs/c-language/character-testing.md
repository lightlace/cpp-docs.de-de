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
ms.openlocfilehash: 89f48346d9b96c7de20c11fd4cbcde106571ed57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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