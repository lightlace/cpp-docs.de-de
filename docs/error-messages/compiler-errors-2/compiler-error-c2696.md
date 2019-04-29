---
title: Compilerfehler C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: 340a5d0596160b6c9c7bcfc78aed812f8c5f3fa3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367602"
---
# <a name="compiler-error-c2696"></a>Compilerfehler C2696

Ein temporäres Objekt von einem verwalteten Typ 'Typ' kann nicht erstellt werden.

Verweise auf `const` in einem nicht verwalteten Programm dazu führen, dass den Compiler rufen Sie den Konstruktor und ein temporäres Objekt erstellt, auf dem Stapel. Eine verwaltete Klasse kann jedoch nie auf dem Stapel erstellt werden.

C2696 ist nur über die veraltete Compileroption erreichbar **oldSyntax**.
