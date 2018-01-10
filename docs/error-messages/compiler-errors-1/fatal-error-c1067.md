---
title: Schwerwiegender Fehler C1067 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1067
dev_langs: C++
helpviewer_keywords: C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8889ccbfcac31917948da719444dab68a2d1b9c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1067"></a>Schwerwiegender Fehler C1067
Compilerlimit: 64 KB für Typeneinträge Größe wurde überschritten  
  
 Dieser Fehler kann auftreten, wenn ein Symbol, das einen ergänzten Namen, die länger als 247 Zeichen aufweist.  Verkürzen Sie den Symbolnamen um zu beheben.  
  
 Wenn der Compiler Debuginformationen generiert, Typeneinträge zum Definieren von Typen, die im Quellcode gefunden.  Typeneinträge enthalten beispielsweise einfache Strukturen und Argumentlisten von Funktionen.  Einige dieser Typ Datensätze können umfangreiche Listen sein.  
  
 Auf die Größe eines beliebigen Typs Datensatzes ist maximal 64 KB.  Wenn dieser 64 KB-Grenze überschritten wird, wird dieser Fehler auftreten.  
  
 C1067 kann auch auftreten, wenn viele Symbole mit langen Namen vorhanden sind oder wenn eine Klasse, Struktur oder Union verfügt über zu viele Member.