---
title: Umwandlungsoperatoren
ms.date: 11/04/2016
helpviewer_keywords:
- cast operators
- type casts, operators
- operators [C++], cast
- type conversion, cast operators
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
ms.openlocfilehash: e3d892a5aede4cd2d6a980b440875f0ac9837120
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147944"
---
# <a name="cast-operators"></a>Umwandlungsoperatoren

Eine Typumwandlung stellt eine Möglichkeit zum expliziten Konvertieren des Typs eines Objekts in einer bestimmten Situation bereit.

## <a name="syntax"></a>Syntax

*cast-expression*: *unary-expression*

**(**  *type-name*  **)**  *cast-expression*

Der Compiler behandelt *cast-expression* als *type-name*-Typ, nachdem eine Typumwandlung vorgenommen wurde. Umwandlungen können verwendet werden, um Objekte eines beliebigen skalaren Typs in einen oder aus einem anderen skalaren Typ zu konvertieren. Explizite Typumwandlungen werden durch dieselben Regeln eingeschränkt, die die Auswirkungen von impliziten Konvertierungen bestimmen, die unter [Zuweisungskonvertierungen](../c-language/assignment-conversions.md) erläutert werden. Zusätzliche Einschränkungen für Typumwandlungen ergeben sich möglicherweise aus den tatsächlichen Größen oder der Darstellung bestimmter Typen. Weitere Informationen zu den tatsächlichen Größen ganzzahliger Typen finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md). Weitere Informationen zu Typumwandlungen finden Sie unter [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md).

## <a name="see-also"></a>Siehe auch

[Umwandlungsoperator](../cpp/cast-operator-parens.md)
