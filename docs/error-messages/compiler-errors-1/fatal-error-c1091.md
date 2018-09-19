---
title: Schwerwiegender Fehler C1091 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1091
dev_langs:
- C++
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e93c2e6c26f8704e700465fb706867129847a460
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104238"
---
# <a name="fatal-error-c1091"></a>Schwerwiegender Fehler C1091

Compilerlimit: Die Zeichenfolge überschreitet die Länge um "Länge" Bytes.

Eine Zeichenfolgekonstante hat die aktuelle Grenze für die Länge von Zeichenfolgen überschritten.

Teilen Sie ggf. die statische Zeichenfolge in zwei (oder mehr) Variablen auf und verwenden Sie [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) , um das Ergebnis im Rahmen der Deklaration oder während der Laufzeit zusammenzuführen.