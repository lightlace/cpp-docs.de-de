---
title: Run-Time-Modell Objektdienste | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cff506d559ab44ba4034e982bb909db763917594
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378294"
---
# <a name="run-time-object-model-services"></a>Objektmodelldienste zur Laufzeit
Die Klassen [CObject](../../mfc/reference/cobject-class.md) und [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) mehrere Objektdienste, einschließlich des Zugriffs auf die Laufzeit Klasseninformationen, Serialisierung und dynamische objekterstellung zu kapseln. Alle Klassen abgeleitet `CObject` erben diese Funktionalität.  
  
 Zugriff auf die Laufzeit Klasseninformationen können Sie Informationen über die Klasse des Objekts zur Laufzeit zu ermitteln. Kann die Klasse eines Objekts zur Laufzeit bestimmt ist nützlich, wenn Sie benötigen zusätzliche Typprüfung von Funktionsargumenten und Sie spezielle Code basierend auf der Klasse eines Objekts schreiben müssen. Laufzeit Klasseninformationen wird direkt von der Programmiersprache C++ nicht unterstützt.  
  
 Serialisierung ist der Prozess des Schreibens oder Lesen des Inhalts eines Objekts in oder aus einer Datei. Sie können Serialisierung verwenden, um Inhalt des Objekts zu speichern, auch nachdem die Anwendung beendet wird. Das Objekt kann dann aus der Datei gelesen werden, wenn die Anwendung neu gestartet wird. Solche Datenobjekte gelten als "persistent".  
  
 Dynamische objekterstellung ermöglicht es Ihnen, ein Objekt einer bestimmten Klasse zur Laufzeit zu erstellen. Beispielsweise müssen Dokument, Ansicht und Frame-Objekte die dynamische Erstellung unterstützen, da das Framework benötigt diese dynamisch erstellen.  
  
 Die folgende Tabelle enthält die MFC-Makros, die zur Laufzeit-Klasseninformationen, Serialisierung und die dynamische Erstellung unterstützen.  
  
 Weitere Informationen zu diesen Laufzeitobjekt Services sowie die Serialisierung finden Sie im Artikel [CObject-Klasse: Zugreifen auf Laufzeit-Klasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="run-time-object-model-services-macros"></a>Run-Time-Objektmodelldienste Makros  
  


|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|Ermöglicht den Zugriff auf Laufzeit-Klasseninformationen (muss in der Klassendeklaration verwendet werden).|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|Ermöglicht die dynamische Erstellung und den Zugriff auf die Laufzeit-Klasseninformationen (muss in der Klassendeklaration verwendet werden).|  
|[DECLARE_SERIAL](#declare_serial)|Ermöglicht die Serialisierung und den Zugriff auf die Laufzeit-Klasseninformationen (muss in der Klassendeklaration verwendet werden).|  
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Ermöglicht den Zugriff auf Laufzeit-Klasseninformationen (muss in der klassenimplementierung verwendet werden).|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Ermöglicht die dynamische Erstellung und den Zugriff auf die Laufzeitinformationen (muss in der klassenimplementierung verwendet werden).|  
|[IMPLEMENT_SERIAL](#implement_serial)|Ermöglicht die Serialisierung und den Zugriff auf die Laufzeit-Klasseninformationen (muss in der klassenimplementierung verwendet werden).|  
|[RUNTIME_CLASS](#runtime_class)|Gibt die `CRuntimeClass` -Struktur, die der benannten Klasse entspricht.|  


 OLE erfordert häufig die dynamische Erstellung von Objekten zur Laufzeit. Beispielsweise muss eine OLE-Server-Anwendung OLE-Elemente dynamisch in Reaktion auf eine Anforderung von einem Client zu erstellen. Auf ähnliche Weise muss ein Automatisierungsservers Elemente in der Antwort auf Anforderungen von Automatisierungsclients erstellen können.  
  
 Die Microsoft Foundation Class-Bibliothek stellt zwei Makros, die bestimmte an OLE bereit.  
  
### <a name="dynamic-creation-of-ole-objects"></a>Die dynamische Erstellung von OLE-Objekte  

 






|||  
|-|-|  
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Bestimmt, ob die Common Controls-Bibliothek die angegebene API implementiert.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Bestimmt, ob die Common Controls-Bibliothek die angegebene API implementiert.|
|[DECLARE_OLECREATE](#declare_olecreate)|Ermöglicht es Objekten, die über OLE-Automatisierung erstellt werden.|  
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Deklariert die **GetUserTypeNameID** und `GetMiscStatus` Memberfunktionen der Control-Klasse.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|Deklariert, dass der OLE-Steuerelements zur Verfügung einer Liste von Eigenschaftenseiten, um ihre Eigenschaften anzuzeigen.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Ermöglicht es Objekten, die von der OLE-System erstellt werden.|  
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Implementiert die **GetUserTypeNameID** und `GetMiscStatus` Memberfunktionen der Control-Klasse.|  
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Entweder dieses Makro oder [IMPLEMENT_OLECREATE](#implement_olecreate) muss in der Implementierungsdatei für jede Klasse, die verwendet werden `DECLARE_OLECREATE`. |

## <a name="afx_comctl32_if_exists"></a> AFX_COMCTL32_IF_EXISTS
Bestimmt, ob die Common Controls-Bibliothek die angegebene API implementiert.  
   
### <a name="syntax"></a>Syntax  
  ```  
AFX_COMCTL32_IF_EXISTS(  proc );  
```
### <a name="parameters"></a>Parameter  
 `proc`  
 Zeiger auf eine Null-terminierte Zeichenfolge, enthält den Namen der Funktion, oder gibt die Funktion Ordinalwert an. Wenn dieser Parameter einen Ordinalwert ist, muss es in das niederwertige Wort sein; das höherwertige Wort muss 0 (null) sein. Dieser Parameter muss im Unicode-Format sein.  
   
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro, um zu bestimmen, ob Common Controls-Bibliothek von die Funktion angegeben `proc` (statt [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212).  
   
### <a name="requirements"></a>Anforderungen  
 afxcomctl32.h, afxcomctl32.inl  
   
### <a name="see-also"></a>Siehe auch  
 [Isolierung der MFC-gängigsten steuert Bibliothek](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)
 
## <a name="afx_comctl32_if_exists2"></a>  AFX_COMCTL32_IF_EXISTS2
Bestimmt, ob die Common Controls-Bibliothek die angegebene API implementiert (Dies ist die Unicode-Version des [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)).  
   
### <a name="syntax"></a>Syntax    
```  
AFX_COMCTL32_IF_EXISTS2( proc );  
```
### <a name="parameters"></a>Parameter  
 `proc`  
 Zeiger auf eine Null-terminierte Zeichenfolge, enthält den Namen der Funktion, oder gibt die Funktion Ordinalwert an. Wenn dieser Parameter einen Ordinalwert ist, muss es in das niederwertige Wort sein; das höherwertige Wort muss 0 (null) sein. Dieser Parameter muss im Unicode-Format sein.  
   
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro, um zu bestimmen, ob Common Controls-Bibliothek von die Funktion angegeben `proc` (statt [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212). Dieses Makro wird die Unicode-Version des `AFX_COMCTL32_IF_EXISTS`.  
   
### <a name="requirements"></a>Anforderungen  
 afxcomctl32.h, afxcomctl32.inl  
   
### <a name="see-also"></a>Siehe auch  
 [Isolierung der MFC-gängigsten steuert Bibliothek](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)



##  <a name="declare_dynamic"></a>  DECLARE_DYNAMIC  
 Fügt die Möglichkeit zur Laufzeit Zugriff auf Informationen über die Klasse eines Objekts beim Ableiten einer Klasse von `CObject`.  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Hinzufügen der `DECLARE_DYNAMIC` Makro an das Modul Headerdateien (. h) für die Klasse und fügen Sie, dass das Modul in allen CPP-Modulen, die Zugriff auf Objekte dieser Klasse benötigt.  
  
 Bei Verwendung der **DECLARE**_ **dynamische** und `IMPLEMENT_DYNAMIC` Makros wie beschrieben, können Sie dann die `RUNTIME_CLASS` Makros und die `CObject::IsKindOf` -Funktion können Sie die Klasse der Objekte zur Laufzeit zu ermitteln Zeit.  
  
 Wenn `DECLARE_DYNAMIC` ist in der Klassendeklaration enthalten `IMPLEMENT_DYNAMIC` in der klassenimplementierung enthalten sein müssen.  
  
 Weitere Informationen zu den `DECLARE_DYNAMIC` -Makro, finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IMPLEMENT_DYNAMIC](#implement_dynamic).  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="declare_dyncreate"></a>  DECLARE_DYNCREATE  
 Aktiviert die Objekte `CObject`-abgeleitete Klassen dynamisch zur Laufzeit erstellt werden.  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Fähigkeit zum dynamischen Erstellen neuer Objekte. Angenommen, die neue Ansicht erstellt, wenn Sie ein neues Dokument zu öffnen. Dokument anzeigen und Frameklassen sollten dynamische Erstellung unterstützen, da das Framework benötigt diese dynamisch erstellen.  
  
 Hinzufügen der `DECLARE_DYNCREATE` Makro im h-Modul für die Klasse und fügen Sie, dass das Modul in allen CPP-Modulen, die Zugriff auf Objekte dieser Klasse benötigt.  
  
 Wenn `DECLARE_DYNCREATE` ist in der Klassendeklaration enthalten `IMPLEMENT_DYNCREATE` in der klassenimplementierung enthalten sein müssen.  
  
 Weitere Informationen zu den `DECLARE_DYNCREATE` -Makro, finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
> [!NOTE]
>  Die `DECLARE_DYNCREATE` Makro enthält sämtliche Funktionen der `DECLARE_DYNAMIC`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IMPLEMENT_DYNCREATE](#implement_dyncreate).  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

 
## <a name="declareolectltype"></a>DECLARE_OLECTLTYPE
Deklariert die **GetUserTypeNameID** und `GetMiscStatus` Memberfunktionen der Control-Klasse.  
   
### <a name="syntax"></a>Syntax    
```
DECLARE_OLECTLTYPE( class_name )  
```
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name des der Control-Klasse.  
   
### <a name="remarks"></a>Hinweise  
 **GetUserTypeNameID** und `GetMiscStatus` sind reine virtuelle Funktionen, die im deklarierten `COleControl`. Da diese Funktionen befinden sich rein virtuell sein, sie müssen überschrieben werden in der Steuerelementklasse. Zusätzlich zu **DECLARE_OLECTLTYPE**, müssen Sie hinzufügen, die `IMPLEMENT_OLECTLTYPE` Makro Ihrer Klassendeklaration Steuerelement.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
   
### <a name="see-also"></a>Siehe auch  
 [IMPLEMENT_OLECTLTYPE](#implement_olectltype)
 

## <a name="declareproppageids"></a>DECLARE_PROPPAGEIDS
Deklariert, dass der OLE-Steuerelements zur Verfügung einer Liste von Eigenschaftenseiten, um ihre Eigenschaften anzuzeigen.  
   
### <a name="syntax"></a>Syntax    
```
DECLARE_PROPPAGEIDS( class_name )  
```
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name des der Control-Klasse, die die Eigenschaftenseiten besitzt.  
   
### <a name="remarks"></a>Hinweise  
 Verwenden der `DECLARE_PROPPAGEIDS` Makro am Ende der Klassendeklaration. Verwenden Sie dann in der CPP-Datei, die die Memberfunktionen für die Klasse definiert die `BEGIN_PROPPAGEIDS` -Makro, Makroeinträge für jede der Eigenschaftenseiten des Steuerelements, und die `END_PROPPAGEIDS` Makro, um das Ende der Eigenschaftenliste Seite zu deklarieren.  
  
 Weitere Informationen zu Eigenschaftenseiten, finden Sie im Artikel [ActiveX-Steuerelemente: Eigenschaftenseiten](../mfc-activex-controls-property-pages.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
   
### <a name="see-also"></a>Siehe auch   
 [BEGIN_PROPPAGEIDS](#begin_proppageids)   
 [END_PROPPAGEIDS](#end_proppageids)

##  <a name="declare_serial"></a>  DECLARE_SERIAL  
 Generiert den Code der C++-Header für eine `CObject`-abgeleitete Klasse, die serialisiert werden kann.  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Serialisierung ist der Prozess der Schreib- und Lesezugriffe auf den Inhalt eines Objekts auf und aus einer Datei.  
  
 Verwenden der `DECLARE_SERIAL` Makro in einem Modul h, und fügen Sie, dass das Modul in allen CPP-Modulen, die Zugriff auf Objekte dieser Klasse benötigt.  
  
 Wenn `DECLARE_SERIAL` ist in der Klassendeklaration enthalten `IMPLEMENT_SERIAL` in der klassenimplementierung enthalten sein müssen.  
  
 Die `DECLARE_SERIAL` Makro enthält sämtliche Funktionen der `DECLARE_DYNAMIC` und `DECLARE_DYNCREATE`.  
  
 Können Sie die **AFX_API** Makro so exportieren Sie automatisch die `CArchive` Extraktionsoperator für Klassen, bei denen die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros. Klammer Klassendeklarationen (befindet sich in der .h-Datei), durch den folgenden Code:  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Weitere Informationen zu den `DECLARE_SERIAL` -Makro, finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="implement_dynamic"></a>  IMPLEMENT_DYNAMIC  
 Den C++-Code für ein dynamisches generiert `CObject`-Klasse mit Laufzeitzugriff auf den Klassennamen und die Position innerhalb der Hierarchie.  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
 `base_class_name`  
 Der Name der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `IMPLEMENT_DYNAMIC` Makro in einer CPP-Modul, und klicken Sie dann links das resultierende Objekt code nur einmal.  
  
 Weitere Informationen finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="implement_dyncreate"></a>  IMPLEMENT_DYNCREATE  
 Aktiviert die Objekte `CObject`-abgeleitete Klassen dynamisch zur Laufzeit erstellt werden Zeit bei Verwendung mit der `DECLARE_DYNCREATE` Makro.  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
 `base_class_name`  
 Der tatsächliche Name der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Fähigkeit zum Erstellen neuer Objekte dynamisch, z. B., wenn während der Serialisierung ein Objekts vom Datenträger gelesen. Hinzufügen der `IMPLEMENT_DYNCREATE` Makro in der Implementierungsdatei der Klasse. Weitere Informationen finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
 Bei Verwendung der `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE` Makros, dann können Sie die `RUNTIME_CLASS` Makros und die `CObject::IsKindOf` Memberfunktion versucht, die Klasse der Objekte zur Laufzeit zu bestimmen.  
  
 Wenn `DECLARE_DYNCREATE` ist in der Klassendeklaration enthalten `IMPLEMENT_DYNCREATE` in der klassenimplementierung enthalten sein müssen.  
  
 Beachten Sie, dass diese Makrodefinition der Standardkonstruktor für die Klasse aufruft. Ein nicht trivialen Konstruktor explizit durch die Klasse implementiert ist, müssen sie auch den Standardkonstruktor auch explizit implementieren. Der Standardkonstruktor der Klasse hinzugefügt werden kann **private** oder **geschützt** Member-Abschnitten, um zu verhindern, die von außerhalb der Implementierung der Klasse aufgerufen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

## <a name="implement_olecreate_flags"></a>  IMPLEMENT_OLECREATE_FLAGS
Entweder dieses Makro oder [IMPLEMENT_OLECREATE](#implement_olecreate) muss in der Implementierungsdatei für jede Klasse, die verwendet werden `DECLARE_OLECREATE`.  
   
### <a name="syntax"></a>Syntax    
```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags, 
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
  
```
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
 *external_name*  
 Der Objektname, der für andere Anwendungen (in Anführungszeichen eingeschlossen) verfügbar gemacht wird.  
  
 `nFlags`  
 Enthält eine oder mehrere der folgenden Flags:  
  
-   `afxRegInsertable` Ermöglicht das Steuerelement im Dialogfeld "Objekt einfügen" für OLE-Objekte angezeigt.    
-   `afxRegApartmentThreading` Legt das Threadingmodell in der Registrierung auf ThreadingModel = Apartment.    
-   **AfxRegFreeThreading** legt das Threadingmodell in der Registrierung auf ThreadingModel = frei.  
  
     Sie können die zwei Flags kombinieren `afxRegApartmentThreading` und `afxRegFreeThreading` festzulegende ThreadingModel = Both. Finden Sie unter [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) in das Windows SDK für Weitere Informationen zum Modell Registrierung threading.    
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8*  
 Komponenten von der Klasse **CLSID**.  
   
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Bei Verwendung von `IMPLEMENT_OLECREATE_FLAGS`, können Sie angeben, welche Threadingmodell, das dem Objekt unterstützt werden, mithilfe der `nFlags` Parameter. Wenn Sie nur das einzelne gehen Modell unterstützen möchten, verwenden Sie `IMPLEMENT_OLECREATE`.  
  
 Der externe Name ist der Bezeichner für andere Anwendungen verfügbar gemacht. Clientanwendungen verwenden den externen Namen auf ein Objekt dieser Klasse von einem Automatisierungsserver anfordern.  
  
 Die OLE-Klassen-ID ist ein eindeutiger 128-Bit-Bezeichner für das Objekt. Es besteht aus einer **lange**, zwei **WORD**s und acht **BYTE**s, dargestellt durch *l*, *w1*, *w2*, und *b1* über *b8* in der syntaxbeschreibung. Die Anwendungs-Assistent und der Code-Assistenten erstellen eindeutiger OLE-Klassen-IDs für Sie nach Bedarf.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [DECLARE_OLECREATE](#declare_olecreate)   
 [CLSID-Schlüssel](http://msdn.microsoft.com/library/windows/desktop/ms691424)


## <a name="implement_olecreate"></a> IMPLEMENT_OLECTLTYPE
Implementiert die **GetUserTypeNameID** und `GetMiscStatus` Memberfunktionen der Control-Klasse.  
   
### <a name="syntax"></a>Syntax    
```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )  
```
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der Name des der Control-Klasse.  
  
 *idsUserTypeName*  
 Die Ressourcen-ID, der eine Zeichenfolge, die den externen Namen des Steuerelements enthält.  
  
 *dwOleMisc*  
 Eine Enumeration, die ein oder mehrere Flags enthält. Weitere Informationen zu dieser Enumeration finden Sie unter [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) im Windows SDK.  
   
### <a name="remarks"></a>Hinweise  
 Zusätzlich zu `IMPLEMENT_OLECTLTYPE`, müssen Sie hinzufügen, die **DECLARE_OLECTLTYPE** Makro Ihrer Klassendeklaration Steuerelement.  
  
 Die **GetUserTypeNameID** Memberfunktion gibt die Ressourcenzeichenfolge, die die Steuerelementklasse identifiziert. `GetMiscStatus` Gibt die **OLEMISC** Bits für das Steuerelement. Diese Enumeration gibt eine Auflistung von Einstellungen für verschiedene Eigenschaften des Steuerelements an. Eine vollständige Beschreibung der **OLEMISC** -Einstellungen finden Sie unter [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) im Windows SDK.  
  
> [!NOTE]
>  Die Standardeinstellungen, die von der ActiveX ControlWizard verwendet werden: **OLEMISC_ACTIVATEWHENVISIBLE**, **OLEMISC_SETCLIENTSITEFIRST**, **OLEMISC_INSIDEOUT**, **OLEMISC_CANTLINKINSIDE**, und **OLEMISC_RECOMPOSEONRESIZE**.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [DECLARE_OLECTLTYPE](#declare_olectltype)

##  <a name="implement_serial"></a>  IMPLEMENT_SERIAL  
 Den C++-Code für ein dynamisches generiert `CObject`-Klasse mit Laufzeitzugriff auf den Klassennamen und die Position innerhalb der Hierarchie.  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
 `base_class_name`  
 Der Name der Basisklasse.  
  
 *wSchema*  
 Ein **"uint"** "Versionsnummer", die im Archiv in ein Deserialisieren Programm zu identifizieren und Behandeln von erstellte Daten aktivieren, codiert werden früher Versionen programmieren. Die Anzahl der Klasse Schema darf nicht-1 sein.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `IMPLEMENT_SERIAL` Makro in einem Modul cpp; dann das resultierende Objektcode nur einmal zu verknüpfen.  
  
 Können Sie die **AFX_API** Makro so exportieren Sie automatisch die `CArchive` Extraktionsoperator für Klassen, bei denen die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL` Makros. Klammer Klassendeklarationen (befindet sich in der .h-Datei), durch den folgenden Code:  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Weitere Informationen finden Sie unter der [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 

##  <a name="runtime_class"></a>  RUNTIME_CLASS  
 Ruft die Run-Time-Klasse-Struktur nicht mit dem Namen einer C++-Klasse.  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse (nicht in Anführungszeichen eingeschlossen).  
  
### <a name="remarks"></a>Hinweise  
 `RUNTIME_CLASS` Gibt einen Zeiger auf eine [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Struktur für die Klasse, die vom angegebenen *Class_name*. Nur `CObject`-abgeleitete Klassen deklariert mit `DECLARE_DYNAMIC`, `DECLARE_DYNCREATE`, oder `DECLARE_SERIAL` zurück Zeiger auf eine `CRuntimeClass` Struktur.  
  
 Weitere Informationen finden Sie unter [CObject-Klasse Themen](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afx.h 
   
##  <a name="declare_olecreate"></a>  DECLARE_OLECREATE  
 Aktiviert die Objekte `CCmdTarget`-abgeleitete Klassen, die über OLE-Automatisierung erstellt werden.  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Mit diesem Makro können andere OLE-fähigen Anwendungen, Objekte dieses Typs zu erstellen.  
  
 Hinzufügen der `DECLARE_OLECREATE` Makro im h-Modul für die Klasse, und fügen Sie, dass das Modul in allen CPP-Modulen, die Zugriff auf Objekte dieser Klasse benötigt.  
  
 Wenn `DECLARE_OLECREATE` ist in der Klassendeklaration enthalten `IMPLEMENT_OLECREATE` in der klassenimplementierung enthalten sein müssen. Eine Klasse Deklaration mit `DECLARE_OLECREATE` auch verwenden, müssen `DECLARE_DYNCREATE` oder `DECLARE_SERIAL`.  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h  

##  <a name="implement_olecreate"></a>  IMPLEMENT_OLECREATE  
 Entweder dieses Makro oder [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) muss in der Implementierungsdatei für jede Klasse, die verwendet werden `DECLARE_OLECREATE`.  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>Parameter  
 *CLASS_NAME*  
 Der tatsächliche Name der Klasse.  
  
 *external_name*  
 Der Objektname, der für andere Anwendungen (in Anführungszeichen eingeschlossen) verfügbar gemacht wird.  
  
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4* , *b5*, *b6*, *b7*, *b8*  
 Komponenten von der Klasse **CLSID**.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Bei Verwendung von `IMPLEMENT_OLECREATE`, in der Standardeinstellung, die Sie unterstützen nur einzelnen Threadingmodells. Bei Verwendung von `IMPLEMENT_OLECREATE_FLAGS`, können Sie angeben, welche Threadingmodell, das dem Objekt unterstützt werden, mithilfe der `nFlags` Parameter.  
  
 Der externe Name ist der Bezeichner für andere Anwendungen verfügbar gemacht. Clientanwendungen verwenden den externen Namen auf ein Objekt dieser Klasse von einem Automatisierungsserver anfordern.  
  
 Die OLE-Klassen-ID ist ein eindeutiger 128-Bit-Bezeichner für das Objekt. Es besteht aus einer **lange**, zwei **WORD**s und acht **BYTE**s, dargestellt durch *l*, *w1*, *w2*, und *b1* über *b8* in der syntaxbeschreibung. Die Anwendungs-Assistent und der Code-Assistenten erstellen eindeutiger OLE-Klassen-IDs für Sie nach Bedarf.  

### <a name="requirements"></a>Anforderungen  
 **Header**: afxdisp.h 

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

