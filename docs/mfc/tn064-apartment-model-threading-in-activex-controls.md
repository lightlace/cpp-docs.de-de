---
title: 'TN064: Apartmentmodellthreading in ActiveX-Steuerelementen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls.activex
dev_langs:
- C++
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a706c927a7aacaf69091d6b448e00bd7938c265f
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950434"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064: Apartmentmodellthreading in ActiveX-Steuerelementen
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 In diesem technischen Hinweis wird erläutert, wie apartmentmodellthreading in ActiveX-Steuerelement zu aktivieren. Beachten Sie, dass apartmentmodellthreading nur in Visual C++-Versionen 4.2 oder höher unterstützt wird.  
  
## <a name="what-is-apartment-model-threading"></a>Was ist Apartmentmodellthreading  
 Das Apartmentmodell besteht ein Ansatz zur Unterstützung von eingebetteter Objekten, wie z. B. ActiveX-Steuerelemente in einer Multithread containeranwendung. Obwohl die Anwendung mehrere Threads möglicherweise, jede Instanz eines eingebetteten Objekts zugewiesen wird, eine "Apartment" die in nur einem Thread ausgeführt wird. Das heißt, erfolgen alle Aufrufe in einer Instanz eines Steuerelements im selben Thread.  
  
 Allerdings können verschiedene Instanzen des gleichen Typs des Steuerelements unterschiedlichen Apartments zugewiesen werden. Also, wenn mehrere Instanzen eines Steuerelements keine Daten gemeinsam (z. B. globale oder statische Daten) freigeben die, Zugriff auf die freigegebenen Daten müssen durch ein Synchronisierungsobjekt, wie einem kritischen Abschnitt geschützt werden sollen.  
  
 Ausführliche Informationen zu den Apartmentthreadingmodell, finden Sie unter [Prozesse und Threads](http://msdn.microsoft.com/library/windows/desktop/ms684841) in der *OLE Programmer's Reference*.  
  
## <a name="why-support-apartment-model-threading"></a>Warum unterstützen Apartmentmodellthreading  
 Steuerelemente, die apartmentmodellthreading unterstützen können im Multithread-containeranwendungen verwendet werden, die auch das Apartmentmodell unterstützen. Wenn Sie die apartmentmodellthreading nicht aktivieren, werden Sie einschränken, den potenziellen Satz von Containern in denen das Steuerelement verwendet werden konnte.  
  
 Aktivieren von apartmentmodellthreading ist für die meisten Steuerelemente einfach, insbesondere, wenn sie wenig oder keine freigegebene Daten haben.  
  
## <a name="protecting-shared-data"></a>Schutz auf freigegebene Daten  
 Wenn das Steuerelement auf freigegebene Daten verwendet z. B. eine statische Membervariable der Zugriff auf die Daten mit einem kritischen Abschnitt, um zu verhindern, dass mehrere Threads Ändern der Daten zur gleichen Zeit geschützt werden soll. Informationen zum Einrichten eines kritischen Abschnitts für diesen Zweck, deklarieren Sie eine statische Membervariable der Klasse `CCriticalSection` in der Klasse des Steuerelements. Verwenden der `Lock` und `Unlock` Memberfunktionen dieser kritischen Abschnitt-Objekt, wo Code auf die freigegebenen Daten zugreift.  
  
 Betrachten Sie z. B. eine Steuerelementklasse, die eine Zeichenfolge, die von allen Instanzen gemeinsam genutzt wird, verwalten muss. Diese Zeichenfolge kann in eine statische Membervariable verwaltet und durch einen kritischen Abschnitt geschützt werden. Das Steuerelement Klassendeklaration würde Folgendes enthalten:  
  
```  
class CSampleCtrl : public COleControl  
{  
 ...  
    static CString _strShared;  
    static CCriticalSection _critSect;  
};  
```  
  
 Die Implementierung für die Klasse würde Definitionen für diese Variablen enthalten:  
  
```  
int CString CSampleCtrl::_strShared;  
CCriticalSection CSampleCtrl::_critSect;  
```  
  
 Der Zugriff auf die `_strShared` statischer Member kann dann durch den kritischen Abschnitt geschützt:  
  
```  
void CSampleCtrl::SomeMethod()  
{  
    _critSect.Lock();
if (_strShared.Empty())  
    _strShared = "<text>";  
    _critSect.Unlock();

 ...  
}  
```  
  
## <a name="registering-an-apartment-model-aware-control"></a>Registriert ein Steuerelement Apartment-Modell-fähig  
 Steuerelemente, die apartmentmodellthreading unterstützen sollte dieser Funktion in der Registrierung durch Hinzufügen des benannten Werts "ThreadingModel" angeben, mit dem Wert "Apartment" ihre Klasse-ID-Registrierungseintrags unter dem *Klassenkennung* \\ **InprocServer32** Schlüssel. Um dazu führen, dass dieser Schlüssel für das Steuerelement automatisch registriert werden, übergeben die *AfxRegApartmentThreading* -Flag in der sechsten Parameter `AfxOleRegisterControlClass`:  
  
```  
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)  
{  
    if (bRegister)  
    return AfxOleRegisterControlClass(
    AfxGetInstanceHandle(), 
    m_clsid, 
    m_lpszProgID, 
    IDS_SAMPLE, 
    IDB_SAMPLE, 
    afxRegApartmentThreading, 
    _dwSampleOleMisc, 
    _tlid, 
    _wVerMajor, 
    _wVerMinor);

 else  
    return AfxOleUnregisterClass(m_clsid,
    m_lpszProgID);

}  
```  
  
 Wenn Steuerelementprojekt vom Steuerelement in Visual C++, Version 4.1 oder höher generiert wurde, wird dieses Flag bereits in Ihrem Code vorhanden sein. Es sind keine Änderungen erforderlich, um das Threadingmodell zu registrieren.  
  
 Wenn das Projekt von einer früheren Version der Assistent generiert wurde, müssen der vorhandene Code einen booleschen Wert als sechsten Parameters. Wenn der vorhandene Parameter auf "true" ist, ändern Sie ihn in *AfxRegInsertable | AfxRegApartmentThreading*. Wenn der vorhandene Parameter auf false festgelegt ist, ändern Sie ihn in *AfxRegApartmentThreading*.  
  
 Wenn das Steuerelement nicht die Regeln für apartmentmodellthreading, müssen Sie nicht übergeben *AfxRegApartmentThreading* in diesem Parameter.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

