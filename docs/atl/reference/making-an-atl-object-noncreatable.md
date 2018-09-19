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
ms.openlocfilehash: cf2b3d047a6618326e69dcb51f143f77fc10c8a6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099537"
---
# <a name="making-an-atl-object-noncreatable"></a>Vornehmen eines ATL-Objekt als nicht erstellbares

Sie können die Attribute eines ATL-basierten COM-Objekts, dass ein Client direkt das Objekt nicht ändern. In diesem Fall wird das Objekt durch einen Methodenaufruf zurückgegeben wird, auf einem anderen Objekt anstatt direkt erstellt.

### <a name="to-make-an-object-noncreatable"></a>Um ein Objekt als nicht erstellbares Objekt zu machen.

1. Entfernen Sie die [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) für das Objekt. Wenn das Objekt als nicht erstellbares Objekt, aber das Steuerelement registriert werden soll, ersetzen Sie Sie mit [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).

2. Hinzufügen der [Noncreatable](../../windows/noncreatable.md) -Attribut auf die Co-Klasse in der IDL-Datei. Zum Beispiel:

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

