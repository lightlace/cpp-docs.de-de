---
title: COM-Unterstützung des Compilers
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: f0b1d6280dc27641287de8fe539cd3a148048245
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154837"
---
# <a name="compiler-com-support"></a>COM-Unterstützung des Compilers

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Der Visual C++-Compiler kann COM(Component Object Model)-Typbibliotheken direkt lesen und den Inhalt in C++-Quellcode übersetzen, der in die Kompilierung aufgenommen werden kann. Es sind Spracherweiterungen verfügbar, um die COM-Programmierung auf der Clientseite zu erleichtern.

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