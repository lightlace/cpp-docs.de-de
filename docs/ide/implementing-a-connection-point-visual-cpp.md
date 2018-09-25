---
title: Implementieren eines Verbindungspunktes (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
- connection points [C++], implementing
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9bba7fdfd44b0a0a97a6d110d2a44b492e1ca449
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429330"
---
# <a name="implementing-a-connection-point-visual-c"></a>Implementieren eines Verbindungspunktes (Visual C++)

Zum Implementieren eines Verbindungspunkts mithilfe des Assistenten zum Implementieren von Verbindungspunkten müssen Sie ein Projekt als eine ATL COM-Anwendung oder eine MFC-Anwendung, die ATL-Unterstützung umfasst, erstellt haben. Sie können den [ATL-Projekt-Assistenten](../atl/reference/atl-project-wizard.md) zum Erstellen einer ATL-Anwendung verwenden, oder [Ihrer MFC-Anwendung ein ATL-Objekt hinzufügen](../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL-Unterstützung in einer MFC-Anwendung zu implementieren.

> [!NOTE]
>  Informationen zum Implementieren von Verbindungspunkten in ein MFC-Projekt finden Sie unter [Connection Points (Verbindungspunkte)](../mfc/connection-points.md).

Nachdem Sie das Projekt erstellt haben, müssen Sie zum Implementieren eines Verbindungspunkts zunächst ein ATL-Objekt hinzufügen. Eine Liste von Assistenten, die Ihrem ATL-Projekt Objekte hinzufügen, finden Sie unter [Adding Objects and Controls to an ATL Project (Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt)](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).

> [!NOTE]
>  Der Assistent unterstützt keine ATL-Dialogfelder, mit einem ATL-Server erstellte XML-Webdienste, Leistungsobjekte oder Leistungsindikatoren.

Ein verbindungsfähiges Objekt (d.h. eine Quelle) kann einen Verbindungspunkt für seine Ausgangsschnittstellen zur Verfügung stellen. Jede Ausgangsschnittstelle kann von einem Client auf einem Objekt (d.h. eine Senke) implementiert werden. Weitere Informationen finden Sie unter [ATL Connection Points (ATL-Verbindungspunkte)](../atl/atl-connection-points.md).

### <a name="to-implement-a-connection-point"></a>So implementieren Sie einen Verbindungspunkt

1. Klicken Sie in der Klassenansicht mit der rechten Maustaste auf den Klassennamen für das ATL-Objekt.

1. Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Verbindungspunkt hinzufügen**, um den [Assistenten zum Implementieren von Verbindungspunkten](../ide/implement-connection-point-wizard.md) anzuzeigen.

1. Wählen Sie die zu implementierenden Verbindungspunktschnittstellen aus den entsprechenden Typbibliotheken aus, und klicken Sie auf **Fertig stellen**.

1. Überprüfen Sie in der Klassenansicht die Proxyklassen, die für jeden Verbindungspunkt erstellt wurden. Die Klassen werden als CProxy*Schnittstellenname*\<T> angezeigt und werden von [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) abgeleitet.

1. Doppelklicken Sie auf die Verbindungspunktklasse, um die Definition der Klasse des Verbindungspunkts anzuzeigen.

   - Wenn Sie einen Verbindungspunkt für die Schnittstelle Ihres eigenen Projekts implementieren, wird die folgende Definition angezeigt.

        ```
        template< class T >
        class CProxyInterfaceName :
           public IConnectionPointImpl< T, &IID_InterfaceName >
        {
        public:
        };
        ```

         If you implement a local interface, methods and properties appear in the class body.

   - Wenn Sie einen Verbindungspunkt für eine andere Schnittstelle implementieren, enthält die Definition die Methoden der Schnittstelle, denen jeweils `Fire_` vorangestellt wurde.

## <a name="see-also"></a>Siehe auch

[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Hinzufügen von Verbindungspunkten zu einem Objekt](../atl/adding-connection-points-to-an-object.md)