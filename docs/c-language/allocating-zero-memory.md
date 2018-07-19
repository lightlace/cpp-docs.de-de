---
title: Nullspeicherbelegung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0de013e9ddd3fb983436bf6ee0db290458936eb5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380637"
---
# <a name="allocating-zero-memory"></a>Nullspeicherbelegung
**ANSI 4.10.3** Das Verhalten der `calloc`-, `malloc`- oder `realloc`-Funktion, wenn die angeforderte Größe Null ist  
  
 Die `calloc`-, `malloc`- und `realloc`-Funktionen akzeptieren Null als Argument. Es wird kein physischer Arbeitsspeicher belegt, jedoch wird ein gültiger Zeiger zurückgegeben, und der Speicherblock kann später durch "realloc" geändert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)