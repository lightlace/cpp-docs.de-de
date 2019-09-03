---
title: inject_statement-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: 25dee621ff8af2c9a39e605b9da2c29d80f9570a
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220996"
---
# <a name="inject_statement-import-attribute"></a>inject_statement-Attribut importieren

**C++Zugeschnitten**

Fügt das Argument als Quelltext in den Header der Typbibliothek ein.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **inject_statement (** "*Source-Text*" **)**

### <a name="parameters"></a>Parameter

*Quelltext*\
In die Headerdatei der Typbibliothek einzufügender Quelltext.

## <a name="remarks"></a>Hinweise

Der Text wird an den Anfang der Namespace Deklaration eingefügt, der den Inhalt der *Typbibliothek* in der Header Datei umschließt.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
