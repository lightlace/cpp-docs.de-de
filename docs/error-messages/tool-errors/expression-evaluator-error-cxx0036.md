---
title: Ausdrucksauswertungsfehler CXX0036 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0036
dev_langs:
- C++
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18e1bf3cda85d7b3d64d51279688a52cec5c0336
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0036"></a>Ausdrucksauswertungsfehler CXX0036
Ungültiger Kontext {...} Angabe  
  
 Diese Meldung kann von einer von mehreren Fehlern bei der Verwendung des Operators Kontext generiert werden (**{}**).  
  
-   Die Syntax der Kontextoperator (**{}**) wurde falsch angegeben.  
  
     Die Syntax des Operators Kontext lautet:  
  
     {*Funktion*,*Modul*,*Dll*}*Ausdruck*  
  
     Dies gibt den Kontext des *Ausdruck*. Der Kontextoperator hat die gleiche Rangfolge und die Verwendung als eine Typumwandlung.  
  
     Nachfolgende Trennzeichen kann ausgelassen werden. Wenn eine der *Funktion*, *Modul*, oder *Dll* enthält ein Komma, müssen Sie den gesamten Namen in Klammern einschließen.  
  
-   Der Funktionsname wurde falsch geschrieben oder im angegebenen Modul oder Dynamic Link Library nicht vorhanden.  
  
     Da C ein Groß-/Kleinschreibung beachtet wird *Funktion* muss in die genaue Groß-/Kleinschreibung erhalten, wie sie in der Quelle definiert ist.  
  
-   Das Modul oder die DLL konnte nicht gefunden werden.  
  
     Überprüfen Sie den vollständigen Pfadnamen des angegebenen Moduls oder der DLL.  
  
 Dieser Fehler ist mit CAN0036 identisch.