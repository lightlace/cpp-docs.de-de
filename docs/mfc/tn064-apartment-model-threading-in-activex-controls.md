---
title: "TN064: Apartmentmodellthreading in ActiveX-Steuerelementen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls.activex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Apartmentmodellthreading"
  - "Container [C++], Multithread"
  - "Multithread-Container"
  - "OLE-Steuerelemente, Containerunterstützung"
  - "TN064"
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN064: Apartmentmodellthreading in ActiveX-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser technische Hinweis wird erläutert, wie Apartmentmodellthreading in einem ActiveX\-Steuerelement aktiviert.  Beachten Sie, dass Apartmentmodellthreading nur Visual C\+\+\-Versionen in 4,2 oder höher unterstützt wird.  
  
## Was ist Apartmentmodellthreading?  
 Das Apartmentmodell ist ein Ansatz zur Unterstützung von eingebetteten Objekten, wie ActiveX\-Steuerelemente, in einer Multithreadanwendung Containeranwendung.  Obwohl die Anwendung mehrere Threads vorhanden sind, wird jede Instanz eines eingebetteten Objekts zu einem Apartment "zugewiesen, wird das" auf nur einem Thread ausgeführt.  Das heißt, geschieht alle Aufrufe in eine Instanz eines Steuerelements im gleichen Thread.  
  
 Es werden verschiedene Instanzen desselben Steuerelementtyps zu unterschiedlichen Apartments zugewiesen werden.  Wenn mehrere Instanzen eines Steuerelements alle Daten in allgemeinen, \(beispielsweise statische oder globale Daten freigeben\), dann müssen Zugriff auf dieses freigegebene Daten über ein Synchronisierungsobjekt, wie einem kritischen Abschnitt geschützt werden.  
  
 Ausführliche Informationen zum Apartmentthreadingmodell, finden Sie unter [Prozesse und Threads](http://msdn.microsoft.com/library/windows/desktop/ms684841) in der *OLE\-Programmierreferenz*.  
  
## Warum unterstützen Sie Apartmentmodellthreading?  
 Steuerelemente, die Apartmentmodellthreading unterstützen, können in den Containeranwendungen verwendet werden, die auch das Apartmentmodell unterstützen.  Wenn Sie nicht Apartmentmodellthreading aktivieren, sollten Sie deshalb ein, das von den Containern festgelegt wird, in denen das Steuerelement verwendet werden kann.  
  
 Apartmentmodellthreading zu aktivieren ist für die meisten Steuerelemente einfach, insbesondere wenn sie wenige oder keine freigegebenen Daten verfügen.  
  
## Schützen der freigegebenen Daten  
 Wenn das Steuerelement Daten freigegebene, wie eine statische Membervariable, Zugriff zu der verwendet, sollten Daten mit einem kritischen Abschnitt geschützt werden, um mehr als einen Thread an die Daten gleichzeitig ändern zu verhindern.  Um einen kritischen Abschnitt zu diesem Zweck erstellen, deklarieren Sie eine statische Membervariable der Klasse `CCriticalSection` der Klasse des Steuerelements.  Verwenden Sie die `Lock` und  **Entsperren**\-Memberfunktionen dieses kritischen Abschnittsobjekts, wo Code auf die freigegebenen Daten zugreift.  
  
 Betrachten Sie zum Beispiel eine Steuerelementklasse, die eine Zeichenfolge verwalten muss, die von allen Instanzen gemeinsam genutzt wird.  Diese Zeichenfolge kann in einer statischen Membervariable verwaltet werden und durch einen kritischen Abschnitt geschützt werden.  Die Klassendeklaration des Steuerelements kann Folgendes enthalten:  
  
```  
class CSampleCtrl : public COleControl  
{  
    ...  
    static CString _strShared;  
    static CCriticalSection _critSect;  
};  
```  
  
 Die Implementierung für die Klasse werden Definitionen für diese Variablen enthalten:  
  
```  
int CString CSampleCtrl::_strShared;  
CCriticalSection CSampleCtrl::_critSect;  
```  
  
 Zugriff auf den statischen Member `_strShared` kann durch den kritischen Abschnitt geschützt dann werden:  
  
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
  
## Registrieren eines Apartment\-Modell\-bewussten Steuerelements  
 Steuerelemente, die Apartmentmodellthreading unterstützen, sollten dieser Funktion in der Registrierung angeben, indem sie dem benannten Wert "ThreadingModel" mit dem Wert "Apartments" in ihrem Klassen\-ID\-Registrierungseintrag unter der *Klassenbezeichner*\\ der **InprocServer32** Schlüssels hinzufügen.  Um dieser Schlüssel zu bewirken für das Steuerelement automatisch registriert werden, übergeben Sie das `afxRegApartmentThreading`\-Flag im 6. Parameter für `AfxOleRegisterControlClass`:  
  
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
        return AfxOleUnregisterClass(m_clsid, m_lpszProgID);  
}  
```  
  
 Wenn das Steuerelementprojekt durch ControlWizard Visual C\+\+\-Version in 4,1 oder höher in generiert wurde, ist dieses Flag bereits im Code vorhanden.  Keine Änderungen sind erforderlich, um das Threadingmodell zu registrieren.  
  
 Wenn das Projekt von einer früheren Version von ControlWizard generiert wurde, wird der vorhandene Code einen booleschen Wert als 6. Parameter.  Wenn der vorhandene Parameter den Wert TRUE ist, ändern Sie ihn in  `afxRegInsertable | afxRegApartmentThreading`.  Wenn der vorhandene FALSCH Parameter ist, ändern Sie ihn in  `afxRegApartmentThreading`.  
  
 Wenn das Steuerelement nicht den Regeln für Apartmentmodellthreading folgt, dürfen Sie `afxRegApartmentThreading` in diesem Parameter nicht übergeben.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)