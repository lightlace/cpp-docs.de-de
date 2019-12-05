---
title: COM-Unterstützung des Compilers
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: 6ab697e5a090158b034a385e60978cff4a73f488
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857579"
---
# <a name="compiler-com-support"></a>COM-Unterstützung des Compilers

**Microsoft-spezifisch**

Der Microsoft C++ -Compiler kann COM-Typbibliotheken (Component Object Model) direkt lesen und den Inhalt C++ in Quellcode übersetzen, der in die Kompilierung aufgenommen werden kann. Spracherweiterungen sind verfügbar, um die COM-Programmierung auf Clientseite für Desktop-Apps zu vereinfachen.

Mithilfe der [#import Präprozessordirektive](../preprocessor/hash-import-directive-cpp.md)kann der Compiler eine Typbibliothek lesen und in eine C++ Header Datei konvertieren, die die COM-Schnittstellen als Klassen beschreibt. Ein Satz von `#import`-Attributen ist für die Benutzersteuerung des Inhalts der resultierenden Typbibliothek-Headerdateien verfügbar.

Sie können das [__declspec](../cpp/declspec.md) Extended-Attribut [UUID](../cpp/uuid-cpp.md) verwenden, um einem COM-Objekt eine Globally Unique Identifier (GUID) zuzuweisen. Das Schlüsselwort [__uuidof](../cpp/uuidof-operator.md) kann zum Extrahieren der einem COM-Objekt zugeordneten GUID verwendet werden. Ein anderes **__declspec** Attribut, [Eigenschaft](../cpp/property-cpp.md), kann verwendet werden, um die `get` und `set` Methoden für einen Datenmember eines COM-Objekts anzugeben.

Eine Reihe von com-Unterstützung für globale Funktionen und Klassen wird bereitgestellt, um die `VARIANT`-und `BSTR` Typen zu unterstützen, intelligente Zeiger zu implementieren und das Fehler Objekt zu kapseln, das von `_com_raise_error`ausgelöst wird:

- [Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)<br/>
[Globale COM-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)
