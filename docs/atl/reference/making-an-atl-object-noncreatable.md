---
title: Vornehmen eines ATL-Objekt als nicht erstellbares | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.objects
dev_langs:
- C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fff45e65fde53d5621d35766e7170c300ee138f9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068475"
---
# <a name="making-an-atl-object-noncreatable"></a>Vornehmen eines ATL-Objekt als nicht erstellbares

Sie können die Attribute eines ATL-basierten COM-Objekts, dass ein Client direkt das Objekt nicht ändern. In diesem Fall wird das Objekt durch einen Methodenaufruf zurückgegeben wird, auf einem anderen Objekt anstatt direkt erstellt.

## <a name="to-make-an-object-noncreatable"></a>Um ein Objekt als nicht erstellbares Objekt zu machen.

1. Entfernen Sie die [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) für das Objekt. Wenn das Objekt als nicht erstellbares Objekt, aber das Steuerelement registriert werden soll, ersetzen Sie Sie mit [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).

1. Hinzufügen der [Noncreatable](../../windows/noncreatable.md) -Attribut auf die Co-Klasse in der IDL-Datei. Zum Beispiel:

    ```
    [uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),
    helpstring("MyObject"),
    noncreatable]
    coclass MyObject
    {
        [default] interface IMyInterface;
    }
    ```

## <a name="see-also"></a>Siehe auch

[ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)<br/>
[Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)<br/>
[Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Grundlagen von ARL COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)
