---
title: Schwerwiegender Fehler C1067 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1067
dev_langs:
- C++
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7ef424de5d375f2d198a5f358976d058d556c506
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1067"></a>Schwerwiegender Fehler C1067
Compilerlimit: 64 KB für Typeneinträge Größe wurde überschritten  
  
 Dieser Fehler kann auftreten, wenn ein Symbol, das einen ergänzten Namen, die länger als 247 Zeichen aufweist.  Verkürzen Sie den Symbolnamen um zu beheben.  
  
 Wenn der Compiler Debuginformationen generiert, Typeneinträge zum Definieren von Typen, die im Quellcode gefunden.  Typeneinträge enthalten beispielsweise einfache Strukturen und Argumentlisten von Funktionen.  Einige dieser Typ Datensätze können umfangreiche Listen sein.  
  
 Auf die Größe eines beliebigen Typs Datensatzes ist maximal 64 KB.  Wenn dieser 64 KB-Grenze überschritten wird, wird dieser Fehler auftreten.  
  
 C1067 kann auch auftreten, wenn viele Symbole mit langen Namen vorhanden sind oder wenn eine Klasse, Struktur oder Union verfügt über zu viele Member.
