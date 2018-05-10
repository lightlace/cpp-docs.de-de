---
title: Zeichentests | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdf65de941486cb8256ba8e30a3f186d3e3702d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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