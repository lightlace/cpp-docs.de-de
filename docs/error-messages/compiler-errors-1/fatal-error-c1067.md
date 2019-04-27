---
title: Schwerwiegender Fehler C1067
ms.date: 11/04/2016
f1_keywords:
- C1067
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
ms.openlocfilehash: f8fe301e25d9ecb5cc67397f9537e0bbd86c0627
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165852"
---
# <a name="fatal-error-c1067"></a>Schwerwiegender Fehler C1067

Compiler-Grenzen: 64 KB für Typeneinträge Größe wurde überschritten

Dieser Fehler kann auftreten, wenn ein Symbol ein ergänzten Namens, der länger als 247 Zeichen aufweist.  Um zu beheben, kürzen Sie den Symbolnamen an.

Wenn der Compiler Debuginformationen generiert werden, werden Typeneinträge zum Definieren von Typen, die im Quellcode gefunden.  Beispielsweise enthalten die Datensätze des Typs einfache Strukturen und Argumentlisten der Funktionen.  Einige diese Datensätze geben können umfangreiche Listen sein.

Es gibt ein Limit von 64 KB auf der Größe eines beliebigen Typs Datensatzes.  Wenn dieser 64-KB-Grenze überschritten wird, wird dieser Fehler auftreten.

C1067 kann auch auftreten, wenn viele Symbole mit langen Namen vorhanden sind oder wenn eine Klasse, Struktur oder Union verfügt über zu viele Elemente.