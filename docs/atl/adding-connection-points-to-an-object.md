---
title: Hinzufügen von Verbindungspunkten zu einem Objekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71f9d136ccdeded02303894195c7b8126acafd9c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356591"
---
# <a name="adding-connection-points-to-an-object"></a>Hinzufügen von Verbindungspunkten zu einem Objekt
Die [ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md) veranschaulicht, wie ein Steuerelement mit Unterstützung für Verbindungspunkte erstellt, zum Hinzufügen von Ereignissen und klicken Sie dann zum Verbindungspunkt zu implementieren. ATL implementiert Verbindungspunkte mit der [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) Klasse.  
  
 Um einen Verbindungspunkt zu implementieren, haben Sie zwei Optionen:  
  
-   Implementieren Sie eigene ausgehenden Ereignisquelle durch Hinzufügen von Verbindungspunkten auf das Steuerelement oder Objekt.  
  
-   Wiederverwenden einer Verbindungspunkt-Schnittstelle in eine andere Typbibliothek definiert.  
  
 In beiden Fällen verwendet der Assistent zum Implementieren von Verbindung eine Typbibliothek Transformationsalgorithmus an.  
  
### <a name="to-add-a-connection-point-to-a-control-or-object"></a>So fügen Sie einen Verbindungspunkt zu einem Steuerelement oder Objekt hinzu  
  
1.  Definieren Sie eine Dispinterface in den bibliotheksblock der IDL-Datei. Wenn Sie Unterstützung für Verbindungspunkte aktiviert, wenn Sie das Steuerelement mit der ATL-Steuerelement-Assistent erstellt, wird die Dispinterface bereits erstellt worden sein. Wenn Sie nicht Unterstützung für Verbindungspunkte aktiviert haben, wenn Sie das Steuerelement erstellt haben, müssen Sie manuell eine Dispinterface der IDL-Datei hinzufügen. Im folgenden ist ein Beispiel für eine Disp-Schnittstelle. Ausgangsschnittstellen sind nicht erforderlich, um die Dispatch-Schnittstellen werden jedoch viele Skriptsprachen wie VBScript und JScript werden muss, damit dieses Beispiel zwei Disp-Schnittstellen verwendet:  
  
     [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]  
  
     Verwenden Sie die uuidgen.exe oder guidgen.exe-Hilfsprogramm zum Generieren eines GUIDs.  
  
2.  Fügen Sie die Dispinterface als die `[default,source]` -Schnittstelle in der Co-Klasse für das Objekt in der IDL-Datei des Projekts. Erneut, wenn Sie Unterstützung für Verbindungspunkte aktiviert, wenn Sie das Steuerelement erstellt, die ATL-Steuerelement-Assistent erstellt die `[default,source`] Eintrag. Um diesen Eintrag manuell hinzuzufügen, fügen Sie die Zeile in Fettschrift angezeigt:  
  
     [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]  
  
     Finden Sie in der IDL-Datei in die [Circ](../visual-cpp-samples.md) ATL-Beispiel für ein Beispiel.  
  
3.  Verwenden Sie Klassenansicht Ereignisschnittstelle Methoden und Eigenschaften hinzu. Mit der rechten Maustaste in der Klasse in der Klassenansicht, zeigen Sie auf **hinzufügen** auf das Kontextmenü, und klicken Sie auf **Verbindungspunkt hinzufügen**.  
  
4.  In der **Schnittstellen** implementieren Connection Point Assistenten die Option im Listenfeld **des Projekts Schnittstellen**. Eine Schnittstelle für das Steuerelement und drücken Sie auf Wunsch **OK**, sehen Sie:  
  
    -   Generieren Sie eine Headerdatei mit eine Proxy-Ereignisklasse, die den Code implementiert, der die ausgehende Aufrufe für das Ereignis erkennen lässt.  
  
    -   Fügen Sie einen Eintrag zur Zuordnung Punkt Verbindung an.  
  
     Sie sehen auch eine Liste aller von Typbibliotheken auf Ihrem Computer. Sie sollten nur anhand einer anderen Typbibliotheken Ihrer Verbindungspunkt definieren, wenn Sie die genaue gleichen Ausgangsschnittstelle in eine andere Typbibliothek gefunden implementieren möchten.  
  
### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>Wiederverwenden von einem Verbindungspunkt-Schnittstelle definiert, in eine andere Typbibliothek  
  
1.  In der Klassenansicht Maustaste eine Klasse, die implementiert eine **BEGIN_COM_MAP** -Makro, zeigen Sie auf **hinzufügen** auf das Kontextmenü, und klicken Sie auf **Verbindungspunkt hinzufügen**.  
  
2.  Im implementieren Connection Point-Assistenten wählen Sie in der Typbibliothek einer Typbibliothek und eine Schnittstelle, und klicken Sie auf **hinzufügen**.  
  
3.  Bearbeiten Sie die IDL-Datei entweder:  
  
    -   Kopieren Sie die Dispinterface aus der IDL-Datei für das Objekt, dessen Ereignisquelle verwendet wird.  
  
    -   Verwenden der **Importlib** Anweisung auf die Typbibliothek.  
  
## <a name="see-also"></a>Siehe auch  
 [Verbindungspunkt](../atl/atl-connection-points.md)

