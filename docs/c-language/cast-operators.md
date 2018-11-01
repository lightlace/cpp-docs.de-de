---
title: Umwandlungsoperatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cast operators
- type casts, operators
- operators [C++], cast
- type conversion, cast operators
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abb4b84519b943d02eca277c9372a128f7d6c2fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098503"
---
# <a name="cast-operators"></a>Umwandlungsoperatoren

Eine Typumwandlung stellt eine Möglichkeit zum expliziten Konvertieren des Typs eines Objekts in einer bestimmten Situation bereit.

## <a name="syntax"></a>Syntax

*cast-expression*: *unary-expression*

**(**  *type-name*  **)**  *cast-expression*

Der Compiler behandelt *cast-expression* als *type-name*-Typ, nachdem eine Typumwandlung vorgenommen wurde. Umwandlungen können verwendet werden, um Objekte eines beliebigen skalaren Typs in einen oder aus einem anderen skalaren Typ zu konvertieren. Explizite Typumwandlungen werden durch dieselben Regeln eingeschränkt, die die Auswirkungen von impliziten Konvertierungen bestimmen, die unter [Zuweisungskonvertierungen](../c-language/assignment-conversions.md) erläutert werden. Zusätzliche Einschränkungen für Typumwandlungen ergeben sich möglicherweise aus den tatsächlichen Größen oder der Darstellung bestimmter Typen. Weitere Informationen zu den tatsächlichen Größen ganzzahliger Typen finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md). Weitere Informationen zu Typumwandlungen finden Sie unter [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md).

## <a name="see-also"></a>Siehe auch

[Umwandlungsoperator](../cpp/cast-operator-parens.md)