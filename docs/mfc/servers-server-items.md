---
title: 'Server: Serverelemente | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e83b75183fe226b4ff384a00b0b5260caba01efa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382501"
---
# <a name="servers-server-items"></a>Server: Serverelemente
Wenn ein Container einen Server gestartet wird, damit ein Benutzer eine eingebettete oder verknüpfte OLE-Element bearbeiten kann, erstellt die Anwendung für die ein "Serverelement". Das Element für Server, die ein Objekt einer Klasse ist abgeleitet von `COleServerItem`, stellt eine Schnittstelle zwischen dem Serverdokument und die containeranwendung.  
  
 Die `COleServerItem` Klasse definiert mehrere überschreibbare Memberfunktionen, die von OLE, in der Regel als Antwort auf Anforderungen aus dem Container aufgerufen werden. Serverelement können Teil des Serverdokuments oder das gesamte Dokument darstellen. Wenn ein OLE-Element im Containerdokument eingebettet ist, stellt der Serverelement die gesamte Serverdokument dar. Wenn das OLE-Element verknüpft ist, kann das Serverelement einen Teil des Serverdokuments oder das gesamte Dokument aus, je nachdem, ob die Verknüpfung an einen Teil oder die gesamte darstellen.  
  
 In der [HIERSVR](../visual-cpp-samples.md) aufnehmen möchten, z. B. die Server-Elementklasse **CServerItem**, verfügt über einen Member, die ein Zeiger auf ein Objekt der Klasse ist **CServerNode**. Die **CServerNode** Objekt ist ein Knoten in der Anwendung HIERSVR-Dokument, das eine Struktur ist. Wenn die **CServerNode** Objekt ist der Stammknoten der **CServerItem** Objekt darstellt, das gesamte Dokument. Wenn die **CServerNode** Objekt ist ein untergeordneter Knoten, die **CServerItem** -Objekt stellt einen Teil des Dokuments dar. Finden Sie im MFC-OLE-Beispiel [HIERSVR](../visual-cpp-samples.md) für ein Beispiel für diese Aktivität.  
  
##  <a name="_core_implementing_server_items"></a> Implementieren von Serverelemente  
 Wenn Sie den Assistenten zum verwenden, um "" Startcode für Ihre Anwendung zu erstellen, ist alles, was Sie tun können, um die Serverelemente in der Startcode enthalten haben eine der Serveroptionen wählen Sie die OLE-Optionsseite. Wenn Sie Serverelemente zu einer vorhandenen Anwendung hinzufügen, führen Sie die folgenden Schritte aus:  
  
#### <a name="to-implement-a-server-item"></a>Um eine Serverelement zu implementieren  
  
1.  Leiten Sie eine Klasse von `COleServerItem` ab.  
  
2.  In der abgeleiteten Klasse überschreiben, die `OnDraw` Memberfunktion.  
  
     Das Framework ruft `OnDraw` zum Rendern des OLE-Elements in einer Metadatei. Die containeranwendung verwendet dieses Metadatei zum Rendern des Elements an. Ihre Anwendung View-Klasse verfügt auch über eine `OnDraw` Memberfunktion, die verwendet wird, zum Rendern des Elements, wenn die Serveranwendung aktiv ist.  
  
3.  Implementieren Sie eine Überschreibung der `OnGetEmbeddedItem` für die Serverdokument Klasse. Weitere Informationen finden Sie im Artikel [Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md) und MFC-OLE-Beispiel [HIERSVR](../visual-cpp-samples.md).  
  
4.  Implementieren Sie der Server-Element-Klasse `OnGetExtent` Memberfunktion. Das Framework ruft diese Funktion, um die Größe des Elements abzurufen. Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> Ein Tipp für Serverelement Architektur  
 Wie in notiert [Serverelement implementieren](#_core_implementing_server_items), Server-Anwendungen müssen in der Lage, Elemente, die sowohl in der Ansicht des Servers als auch in eine Steuerelementcontainer-Anwendung verwendeten Metadatei zu rendern. In der Microsoft Foundation Class Library Anwendungsarchitektur, Ansichtsklasse des `OnDraw` Memberfunktion rendert das Element aus, wenn er bearbeitet wird (finden Sie unter [CView:: OnDraw](../mfc/reference/cview-class.md#ondraw) in der *Referenz zur Klassenbibliothek* ). Das Serverelement `OnDraw` rendert das Element in einer Metadatei in allen anderen Fällen (siehe [COleServerItem:: OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)).  
  
 Duplizieren von Code zu vermeiden, Schreiben Hilfsfunktionen in Ihrem Server Dokumentklasse und Aufrufen von der `OnDraw` Funktionen in Ihrer Ansicht und Serverelement Klassen. Das MFC-OLE-Beispiel [HIERSVR](../visual-cpp-samples.md) verwendet diese Strategie: die Funktionen **CServerView:: OnDraw** und **CServerItem:: OnDraw** beide rufen **CServerDoc::DrawTree**  zum Rendern des Elements.  
  
 Die Ansicht und das Element enthalten `OnDraw` Memberfunktionen, da sie unter verschiedenen Bedingungen zeichnen. Die Sicht muss berücksichtigen als vergrößern/verkleinern, Auswahlgröße und dem Wertebereich, Clipping und Benutzeroberflächenelemente wie z. B. Bildlaufleisten Faktoren. Das Serverelement andererseits, immer des gesamte OLE-Objekts.  
  
 Weitere Informationen finden Sie unter [CView:: OnDraw](../mfc/reference/cview-class.md#ondraw), [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerItem:: OnDraw](../mfc/reference/coleserveritem-class.md#ondraw), und [COleServerDoc::OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)in der *Class Library Reference*.  
  
## <a name="see-also"></a>Siehe auch  
 [Server](../mfc/servers.md)

