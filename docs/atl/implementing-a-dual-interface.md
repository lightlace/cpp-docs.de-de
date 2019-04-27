---
title: Implementieren einer dualen Schnittstelle (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: ecd6a0cc90ca4175c4ae898f2e9aa8bf00508a3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262228"
---
# <a name="implementing-a-dual-interface"></a>Implementieren einer dualen Schnittstelle

Sie implementieren können, eine duale Schnittstelle mit der [IDispatchImpl](../atl/reference/idispatchimpl-class.md) -Klasse, die in einer standardmäßigen Implementierung von bietet die `IDispatch` Methoden in eine duale Schnittstelle. Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

Diese Klasse verwenden zu können:

- Definieren Sie die duale Schnittstelle in einer Typbibliothek.

- Leiten Sie eine Klasse aus einer Spezialisierung von `IDispatchImpl` (übergeben von Informationen über die Schnittstelle und den Typ der Bibliothek als Vorlagenargumente).

- Fügen Sie einen Eintrag (oder Einträge), der COM-Zuordnung, die duale Schnittstelle über verfügbar zu machen `QueryInterface`.

- Implementieren Sie die Vtable-Teil der Schnittstelle in Ihrer Klasse.

- Stellen Sie sicher, dass die Typbibliothek, die mit der Schnittstellendefinition, die zur Laufzeit an Ihren Objekten verfügbar ist.

## <a name="atl-simple-object-wizard"></a>ATL-Assistent für einfache Objekte

Wenn Sie eine neue Schnittstelle und eine neue Klasse für die Implementierung erstellen möchten, können Sie mithilfe der [Dialogfeld ATL-Klasse hinzufügen](../ide/add-class-dialog-box.md), und klicken Sie dann die [ATL-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md).

## <a name="implement-interface-wizard"></a>Assistent zum Implementieren von Schnittstellen

Wenn Sie eine vorhandene Schnittstelle verfügen, können Sie die [Assistent zum Implementieren von Schnittstellen](../atl/reference/adding-a-new-interface-in-an-atl-project.md) die erforderlichen Basisklasse, COM-Zuordnungseinträgen und Skelett methodenimplementierungen zu einer vorhandenen Klasse hinzufügen.

> [!NOTE]
>  Müssen Sie möglicherweise die generierte Basisklasse so anpassen, dass die Versionsnummern der Haupt- und Nebenversionsnummer der Typbibliothek als Vorlagenargumente zu übergeben, werden Ihre `IDispatchImpl` Basisklasse. Der Assistent zum Implementieren von Schnittstellen prüft nicht die Versionsnummer der Typbibliothek für Sie.

## <a name="implementing-idispatch"></a>Implementieren der IDispatch

Können Sie eine `IDispatchImpl` Basisklasse, um eine Implementierung eine Disp-Schnittstelle bereitstellen, indem Sie einfach den entsprechenden Eintrag in der COM-Zuordnung angeben (mithilfe der [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) oder [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) Makro) solange man eine Typbibliothek, die eine entsprechende duale Schnittstelle beschreibt. Es ist durchaus üblich, implementieren die `IDispatch` auf diese Weise z. B. Schnittstelle. Die ATL-Assistent für einfache Objekte und implementieren Assistent Schnittstelle für beide wird davon ausgegangen, dass Sie implementieren möchten `IDispatch` auf diese Weise können also diese fügt des entsprechenden Eintrags zur Zuordnung.

> [!NOTE]
>  ATL bietet die [IDispEventImpl](../atl/reference/idispeventimpl-class.md) und [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) Klassen, die Sie die Disp-Schnittstellen implementieren, ohne dass eine Typbibliothek, die mit der Definition der eine duale Schnittstelle unterstützen.

## <a name="see-also"></a>Siehe auch

[Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)
