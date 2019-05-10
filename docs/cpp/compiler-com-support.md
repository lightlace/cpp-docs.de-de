---
title: COM-Unterstützung des Compilers
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: e13874bad44610821bed9c588af6bd9124162116
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222208"
---
# <a name="compiler-com-support"></a>COM-Unterstützung des Compilers

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Microsoft C++ Compiler direkt lesen Komponente Objekt Model (COM) Typbibliotheken und übersetzt den Inhalt in C++ Quellcode, die in die Kompilierung aufgenommen werden kann. Es sind Spracherweiterungen verfügbar, um die COM-Programmierung auf der Clientseite zu erleichtern.

Mithilfe der [#import-präprozessoranweisung](../preprocessor/hash-import-directive-cpp.md), der Compiler kann eine Typbibliothek lesen und konvertiert ihn in eine C++-Headerdatei, die beschreibt, die COM-als Schnittstellen Klassen. Ein Satz von `#import`-Attributen ist für die Benutzersteuerung des Inhalts der resultierenden Typbibliothek-Headerdateien verfügbar.

Sie können der [__declspec](../cpp/declspec.md) erweitertes Attribut [Uuid](../cpp/uuid-cpp.md) ein COM-Objekt einen global eindeutigen Bezeichner (GUID) zuweisen. Das Schlüsselwort [__uuidof](../cpp/uuidof-operator.md) können verwendet werden, um die COM-Objekt zugeordnete GUID zu extrahieren. Eine andere **__declspec** Attribut [Eigenschaft](../cpp/property-cpp.md), kann verwendet werden, um anzugeben der `get` und `set` Methoden für einen Datenmember eines COM-Objekts.

Ein Satz von COM-Unterstützung globale Funktionen und Klassen dient zur Unterstützung der `VARIANT` und `BSTR` Typen, intelligente Zeiger zu implementieren und zu kapseln die Error-Objekt, das ausgelöst wird, indem `_com_raise_error`:

- [Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)<br/>
[Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)