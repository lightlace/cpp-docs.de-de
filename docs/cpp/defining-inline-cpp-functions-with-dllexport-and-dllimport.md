---
title: Definieren von C++-Inlinefunktionen mit Dllexport und Dllimport | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inline functions [C++], defining
- functions [C++], defining inline
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
ms.assetid: 3b48678b-e7b8-4eda-bb46-b5d34dcf7817
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 165f110a7464e3393c68a469f1ad1220ef174452
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412318"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>Definieren von C++-Inlinefunktionen mit dllexport und dllimport
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Sie können eine Funktion mit dem `dllexport`-Attribut als inline definieren. In diesem Fall wird die Funktion immer instanziiert und exportiert, unabhängig davon, ob ein beliebiges Modul im Programm auf die Funktion verweist oder nicht. Die Funktion wurde vermutlich von einem anderen Programm importiert.  
  
 Sie können auch eine Funktion als inline definieren, die mit dem **dllimport**-Attribut deklariert wurde. In diesem Fall kann die Funktion (gemäß den /Ob-Spezifikationen) erweitert, aber niemals instanziiert werden. Insbesondere bei Verwendung der Adresse der inline-importierten Funktion wird die Adresse der Funktion in der DLL zurückgegeben. Dieses Verhalten stimmt mit der Übernahme der Adresse einer nicht-inline importierten Funktion überein.  
  
 Diese Regeln gelten für Inlinefunktionen, deren Definitionen innerhalb einer Klassendefinition angezeigt werden. Darüber hinaus behalten statische lokale Daten und Zeichenfolgen in Inlinefunktionen die gleichen Identitäten zwischen der DLL und dem Client wie in einem einzelnen Programm (d. h. eine ausführbare Datei ohne DLL-Schnittstelle).  
  
 Lassen Sie beim Bereitstellen von importierten Inlinefunktionen Sorgfalt walten. Gehen Sie beispielsweise beim Aktualisieren der DLL nicht davon aus, dass der Client die geänderte Version der DLL verwendet. Um sicherzustellen, dass Sie die richtige Version der DLL laden, erstellen Sie auch den DLL-Client neu.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)