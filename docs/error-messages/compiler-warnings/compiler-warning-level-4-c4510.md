---
title: Compilerwarnung (Stufe 4) C4510
description: Compilerwarnung C4510 Beschreibung und Projekt Mappe.
ms.date: 09/22/2019
f1_keywords:
- C4510
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
ms.openlocfilehash: 05a6d0fe42d8247d3328506d8772b2fa77b5703c
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71230386"
---
# <a name="compiler-warning-level-4-c4510"></a>Compilerwarnung (Stufe 4) C4510

> "*Klasse*": Standardkonstruktor konnte nicht generiert werden.

Der Compiler kann keinen Standardkonstruktor für die angegebene Klasse generieren, die über keine benutzerdefinierten Konstruktoren verfügt. Objekte dieses Typs können nicht erstellt werden.

Es gibt mehrere Situationen, in denen verhindert wird, dass der Compiler einen Standardkonstruktor erzeugt, einschließlich:

- Ein **konstanter** Datenmember.

- Ein Datenmember, der ein Verweis ist.

Um dieses Problem zu beheben, erstellen Sie einen benutzerdefinierten Standardkonstruktor für die Klasse, die diese Member initialisiert.
