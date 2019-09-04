---
title: Import Attribut ausschließen
ms.date: 08/29/2019
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: 6a3625ee0dd44f3e2731e1240fea5f3dd4ed109e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218722"
---
# <a name="exclude-import-attribute"></a>Import Attribut ausschließen

**C++Zugeschnitten**

Schließt Elemente aus den Headerdateien der Typbibliothek aus, die generiert werden.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **Exclude (** "*Name1*" [ **,** "*name2*"...] **)**

### <a name="parameters"></a>Parameter

*Name1*\
Erstes auszuschließendes Element.

*Name2*\
Optionale Zweite und spätere Elemente, die ggf. ausgeschlossen werden sollen.

## <a name="remarks"></a>Hinweise

Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. Dieses Attribut kann eine beliebige Anzahl von Argumenten annehmen, wobei jedes ein Typbibliotheks Element der obersten Ebene ist, das ausgeschlossen werden soll.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
