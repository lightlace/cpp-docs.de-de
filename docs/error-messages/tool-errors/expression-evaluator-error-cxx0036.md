---
title: Ausdrucksauswertungsfehler CXX0036 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0036
dev_langs:
- C++
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fdf6ddf412786a53ec8da995c2824274da2da3b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0036"></a>Ausdrucksauswertungsfehler CXX0036
Ungültiger Kontext {...} Angabe  
  
 Diese Meldung kann von einer von mehreren Fehlern bei der Verwendung des Operators Kontext generiert werden (**"{}"**).  
  
-   Die Syntax der Kontextoperator (**"{}"**) wurde falsch angegeben.  
  
     Die Syntax des Operators Kontext lautet:  
  
     {*Funktion*,*Modul*,*Dll*}*Ausdruck*  
  
     Dies gibt den Kontext des *Ausdruck*. Der Kontextoperator hat die gleiche Rangfolge und die Verwendung als eine Typumwandlung.  
  
     Nachfolgende Trennzeichen kann ausgelassen werden. Wenn eine der *Funktion*, *Modul*, oder *Dll* enthält ein Komma, müssen Sie den gesamten Namen in Klammern einschließen.  
  
-   Der Funktionsname wurde falsch geschrieben oder im angegebenen Modul oder Dynamic Link Library nicht vorhanden.  
  
     Da C ein Groß-/Kleinschreibung beachtet wird *Funktion* muss in die genaue Groß-/Kleinschreibung erhalten, wie sie in der Quelle definiert ist.  
  
-   Das Modul oder die DLL konnte nicht gefunden werden.  
  
     Überprüfen Sie den vollständigen Pfadnamen des angegebenen Moduls oder der DLL.  
  
 Dieser Fehler ist mit CAN0036 identisch.