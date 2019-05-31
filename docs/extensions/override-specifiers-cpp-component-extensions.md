---
title: Überschreibungsspezifizierer (C++/CLI und C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
ms.openlocfilehash: c1e8e7db2879b0226eaff562f5b5b826bce14caf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515745"
---
# <a name="override-specifiers--ccli-and-ccx"></a>Überschreibungsspezifizierer (C++/CLI und C++/CX)

*Überschreibungsspezifizierer* ändern die Art und Weise, wie sich von geerbten Typen geerbte Typen und Member in abgeleiteten Typen verhalten.

## <a name="all-runtimes"></a>Alle Laufzeiten

### <a name="remarks"></a>Anmerkungen

Weitere Informationen zu Überschreibungsspezifizierern finden Sie unter:

- [abstract](abstract-cpp-component-extensions.md)

- [new (neuer Slot in vtable)](new-new-slot-in-vtable-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- [Überschreibungsspezifizierer und native Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)

**abstract** und **sealed** sind auch in Typdeklarationen gültig, in denen sie nicht als Überschreibungsspezifizierer auftreten.

Informationen zu den Funktionen zum expliziten Überschreiben von Basisklassen finden Sie unter [Explizite Überschreibungen](explicit-overrides-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows-Runtime

(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows-Runtime gelten.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Common Language Runtime gelten.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](component-extensions-for-runtime-platforms.md)