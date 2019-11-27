---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: c3a04f68b7fd17b2b6459c219a98fd99ec2d62d4
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397254"
---
# <a name="local-masm"></a>LOCAL (MASM)

In der ersten Direktive definiert **local** innerhalb eines Makros Bezeichnungen, die für jede Instanz des Makros eindeutig sind.

## <a name="syntax"></a>Syntax

> **Local** *localname* ⟦, *localname* ... ⟧
>
> **Lokale** *Bezeichnung* ⟦ __\[__ *Anzahl* __]__ ⟧ ⟦ __:__ *Typ*⟧ ⟦ __,__ *Bezeichnung* ⟦ __\[__ *count* __]__ *⟧ ⟦ ⟧* ... ⟧

## <a name="remarks"></a>Hinweise

In der zweiten-Direktive erstellt in einer Prozedur Definition (**proc**) in der **lokalen** Prozedur Stapel basierte Variablen, die für die Dauer der Prozedur vorhanden sind. Die *Bezeichnung* kann eine einfache Variable oder ein Array sein, das *count* -Elemente enthält.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
