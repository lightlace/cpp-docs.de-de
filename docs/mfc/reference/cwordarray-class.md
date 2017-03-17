---
title: CWordArray Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- INT
- UINT
- indexed arrays
- arrays [C++], indexed
- WORD data type
- CWordArray class
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cd6c26c49c6b46449ec6d7da42b9166d17d563da
ms.lasthandoff: 02/24/2017

---
# <a name="cwordarray-class"></a>CWordArray-Klasse
Unterstützt Arrays mit 16-Bit-Wörtern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWordArray : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
 Die Memberfunktionen von `CWordArray` ähneln den Memberfunktionen der Klasse [CObArray](../../mfc/reference/cobarray-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CObArray`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo ein [CObject](../../mfc/reference/cobject-class.md) Zeiger als Funktionsparameter oder Rückgabewert, ersetzen Sie durch eine **WORD**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 Beispielsweise übersetzt zu  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Erstellt ein leeres Array.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Fügt am Ende des Arrays ein Element hinzu; vergrößert das Array bei Bedarf.|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Hängt ein anderes Array an das Array an; vergrößert das Array bei Bedarf.|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Gibt den gesamten nicht verwendeten Arbeitsspeicher über der aktuellen Obergrenze frei.|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Gibt den Wert an einem bestimmten Index zurück.|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Ermöglicht den Zugriff auf Elemente im Array. Kann **NULL**.|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Ruft die Anzahl der Elemente im Array ab.|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|Gibt den größten gültigen Index zurück.|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Fügt ein Element (oder alle Elemente in einem anderen Array) am angegebenen Index ein.|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Bestimmt, ob das Array leer ist.|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Entfernt alle Elemente aus diesem Array.|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Entfernt ein Element an einem spezifischen Index.|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Legt den Wert für einen bestimmten Index fest; Array darf nicht vergrößert werden.|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Legt den Wert für einen bestimmten Index fest; vergrößert das Array bei Bedarf.|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Legt die Anzahl der Elemente im Array fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CObArray::operator&#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|Legt das Element am angegebenen Index fest oder ruft es ab.|  
  
## <a name="remarks"></a>Hinweise  
 `CWordArray`enthält die [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro zur Unterstützung der Serialisierung und Sicherung der Elemente. Wenn ein Array von Wörtern befindet sich in ein Archiv, das entweder mit einem überladenen Operator zum Einfügen oder mit der [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) Memberfunktion jedes Element ist, was wiederum serialisiert.  
  
> [!NOTE]
>  Vor dem Verwenden eines Arrays, verwenden Sie `SetSize`, um dessen Größe festzustellen, und weisen dafür Arbeitsspeicher zu. Wenn Sie `SetSize` nicht verwenden, kann das Hinzufügen von Elementen zu Ihrem Array dazu führen, dass es häufig neu zugeordnet und kopiert wird. Häufige Neuzuordnungen und Kopiervorgänge sind ineffizient und können zu einer Fragmentierung des Arbeitsspeichers führen.  
  
 Wenn Sie ein Abbild der einzelnen Elemente im Array benötigen, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Weitere Informationen zur Verwendung von `CWordArray`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CWordArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
##  <a name="icommandsource_interface"></a>ICommandSource-Schnittstelle  
 Verwaltet die Befehle, die von einem Befehlsquellobjekt zu einem Benutzersteuerelement gesendet.  
  
```  
interface class ICommandSource  
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann. Durch implementieren, Sie geben dem Benutzersteuerelement einen Verweis auf die `ICommandSource` Objekt.  
  
 Finden Sie unter [Gewusst wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler  
 Fügt einen Befehlshandler zu einem Befehlsobjekt für die Quelle an.  
  
```  
void AddCommandHandler(
    unsigned int cmdID,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
  
 `cmdHandler`  
 Ein Handle für die Handlermethode Befehl.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt den Befehlshandler `cmdHandler` auf das Befehlsquellobjekt und ordnet Sie den Ereignishandler `cmdID`.  
  
 Finden Sie unter [Gewusst wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `AddCommandHandler`.  
  
##  <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler  
 Ein Befehlsquellobjekt wird eine Gruppe von Befehlshandler hinzugefügt.  
  
```  
void AddCommandRangeHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdIDMin`  
 Der Anfangsindex der Befehls-ID-Bereich.  
  
 `cmdIDMax`  
 Der Endindex der Befehls-ID-Bereich.  
  
 `cmdHandler`  
 Ein Handle für den Message-Handler-Methode, die die Befehle zugeordnet sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs einem einzelnen Meldungshandler und das Befehlsquellobjekt hinzugefügt. Dies wird für die Behandlung einer Gruppenstatus von verwandten Schaltflächen mit einer Methode verwendet.  
  
##  <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler  
 Ein Befehlsquellobjekt hinzugefügt eine Gruppe von Benutzer-Schnittstelle Befehl Meldungshandler.  
  
```  
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,   
    unsigned int cmdIDMax,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdIDMin`  
 Der Anfangsindex der Befehls-ID-Bereich.  
  
 `cmdIDMax`  
 Der Endindex der Befehls-ID-Bereich.  
  
 `cmdHandler`  
 Ein Handle für den Message-Handler-Methode, die die Befehle zugeordnet sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ordnet einen zusammenhängenden Bereich von Befehls-IDs einen einzelnen Benutzer Schnittstelle Befehl Message-Handler und das Befehlsquellobjekt hinzugefügt. Dies wird für die Behandlung einer Gruppenstatus von verwandten Schaltflächen mit einer Methode verwendet.  
  
##  <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler  
 Ein Befehlsquellobjekt hinzugefügt einen Benutzer Schnittstelle Befehl Message-Handler.  
  
```  
void AddCommandUIHandler(
    unsigned int cmdID,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
  
 `cmdUIHandler`  
 Ein Handle für den Benutzer Schnittstelle Befehl Message-Handler-Methode.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt den Benutzer Schnittstelle Befehl Message-Handler `cmdHandler` auf das Befehlsquellobjekt und ordnet Sie den Ereignishandler `cmdID`.  
  
##  <a name="postcommand"></a>ICommandSource::PostCommand  
 Sendet eine Nachricht ohne zu warten, bis sie verarbeitet werden.  
  
```  
void PostCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Parameter  
 `command`  
 Die Befehls-ID der Nachricht bereitgestellt wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode asynchron sendet die Nachricht an die angegebene ID zugeordnet `command`. Sie ruft [CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage) um die Nachricht in der Warteschlange und gibt dann des Fensters zu platzieren, ohne zu warten, für das entsprechende Fenster zum Verarbeiten der Nachricht.  
  
##  <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler  
 Entfernt einen Befehlshandler von einem Befehl-Quellobjekt.  
  
```  
void RemoveCommandHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt die Befehlshandler zugeordnet `cmdID` aus dem Befehlsquellobjekt.  
  
##  <a name="removecommandrangehandler"></a>ICommandSource::RemoveCommandRangeHandler  
 Entfernt eine Gruppe von Befehlshandler von einem Befehl-Quellobjekt.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdIDMin`  
 Der Anfangsindex der Befehls-ID-Bereich.  
  
 `cmdIDMax`  
 Der Endindex der Befehls-ID-Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt eine Gruppe von Message-Handler zugeordnet, durch die Befehls-IDs angegeben `cmdIDMin` und `cmdIDMax`, aus dem Befehlsquellobjekt.  
  
##  <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler  
 Entfernt eine Gruppe von Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdIDMin`  
 Der Anfangsindex der Befehls-ID-Bereich.  
  
 `cmdIDMax`  
 Der Endindex der Befehls-ID-Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt eine Gruppe von Benutzer-Schnittstelle Befehl Message Handler zugeordnet, durch die Befehls-IDs angegeben `cmdIDMin` und `cmdIDMax`, aus dem Befehlsquellobjekt.  
  
##  <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler  
 Entfernt einen Benutzer Schnittstelle Befehlshandler Nachricht von einem Befehl-Quellobjekt.  
  
```  
void RemoveCommandUIHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt den Benutzer Schnittstelle Befehl-Meldungshandler zugeordnet `cmdID` aus dem Befehlsquellobjekt.  
  
##  <a name="sendcommand"></a>ICommandSource::SendCommand  
 Sendet eine Nachricht und wartet vor der Rückgabe verarbeitet werden.  
  
```  
void SendCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Parameter  
 `command`  
 Die Befehls-ID der Nachricht gesendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die Nachricht an die angegebene ID zugeordnet synchron `command`. Sie ruft [Funktion CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) , platzieren Sie die Nachricht in des Fensters Meldungswarteschlange und wartet, bis diese Fensterprozedur die Nachricht vor der Rückgabe verarbeitet hat.  
  
##  <a name="icommandtarget_interface"></a>ICommandTarget-Schnittstelle  
 Stellt ein Benutzersteuerelement mit einer Schnittstelle zum Empfangen von Befehlen aus einem Befehlsquellobjekt bereit.  
  
```  
interface class ICommandTarget  
```  
  
### <a name="remarks"></a>Hinweise  
 Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle (z. B. Frame Menüelemente und Symbolleisten-Schaltflächen) verarbeiten kann. Durch die Implementierung `ICommandTarget`, geben Sie dem Benutzersteuerelement einen Verweis auf das Objekt.  
  
 Finden Sie unter [Gewusst wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `ICommandTarget`.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="initialize"></a>ICommandTarget:: Initialize  
 Initialisiert das Zielobjekt für den Befehl.  
  
```  
void Initialize(ICommandSource^ cmdSource);
```  
  
### <a name="parameters"></a>Parameter  
 `cmdSource`  
 Ein Handle für das Befehlsquellobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Beim Hosten eines Benutzersteuerelements in MFC-Ansicht, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) Routen Befehle und Update-Befehl UI-Nachrichten auf das Benutzersteuerelement, damit Sie die MFC-Befehle zu verarbeiten kann.  
  
 Diese Methode initialisiert die Ziel-Befehlsobjekt und das Quellobjekt für den angegebenen Befehl ordnet `cmdSource`. Es sollte in die Implementierung des Benutzersteuerelements Klasse aufgerufen werden. Bei der Initialisierung, sollten Sie registrieren Befehlshandler das Befehlsquellobjekt durch Aufrufen von [ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md) in der `Initialize` Implementierung. Finden Sie unter [Gewusst wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ein Beispiel zum Verwenden von `Initialize` dazu.  
  
##  <a name="icommandui_interface"></a>ICommandUI-Schnittstelle  
 Verwaltet von Befehlen der Benutzeroberfläche.  
  
```  
interface class ICommandUI  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Schnittstelle stellt Methoden und Eigenschaften, die von Befehlen der Benutzeroberfläche verwalten. `ICommandUI`ähnelt dem [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md), außer dass `ICommandUI` für MFC-Anwendung, die mit .NET Komponenten Zusammenwirken verwendet wird.  
  
 `ICommandUI`wird verwendet, in einer `ON_UPDATE_COMMAND_UI` Handler in einer - abgeleiteten Klasse. Wenn ein Benutzer einer Anwendung (aktiviert oder Klicks) aktiviert wird ein Menü, jedes Menüelement angezeigt, als aktiviert oder deaktiviert. Das Ziel der einzelnen Menübefehle bietet diese Informationen durch die Implementierung einer `ON_UPDATE_COMMAND_UI` Handler. Verwenden Sie das Fenster Eigenschaften für jeden Befehl Schnittstelle Benutzerobjekte in Ihrer Anwendung Meldungszuordnungseintrags und Funktionsprototyp für jeden Handler erstellen.  
  
 Weitere Informationen darüber, wie der `ICommandUI` Schnittstelle in Befehlsrouting verwendet wird, finden Sie unter [Gewusst wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Weitere Informationen dazu, wie Benutzeroberflächenbefehlen in MFC verwaltet werden, finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="check"></a>ICommandUI::Check  
 Legt die Benutzer-Interface-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.  
  
```  
property UICheckState Check;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft legt die Benutzer-Interface-Element für diesen Befehl an den entsprechenden Aktivierungszustand. Legen Sie `Check` auf die folgenden Werte:  
  
|Begriff|Definition|  
|----------|----------------|  
|0|Deaktivieren|  
|1|Aktivieren|  
|2|Legen Sie unbestimmt|  
  
##  <a name="continuerouting"></a>ICommandUI::ContinueRouting  
 Weist den Befehl Weiterleitungsmechanismus routing der aktuellen Nachricht der Vererbungskette Handler fortgesetzt.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine erweiterte Memberfunktion, die in Verbindung mit verwendet werden, sollte ein [ON_COMMAND_EX](http://msdn.microsoft.com/library/0bb49090-aee8-4203-87c8-dd001d3dd26e) Handler, der zurückgibt `FALSE`. Weitere Informationen finden Sie unter Technische Hinweis [TN006: Meldungszuordnungen](../../mfc/tn006-message-maps.md).  
  
##  <a name="enabled"></a>ICommandUI::Enabled  
 Aktiviert oder deaktiviert die Benutzer-Interface-Element für diesen Befehl.  
  
```  
property bool Enabled;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft aktiviert bzw. deaktiviert das User Interface-Element für diesen Befehl. Legen Sie `Enabled` auf `TRUE` aktivieren Sie das Element `FALSE` deaktivieren.  
  
##  <a name="id"></a>ICommandUI::ID  
 Ruft die ID des das Benutzeroberflächenobjekt, dargestellt durch die `ICommandUI` Objekt.  
  
```  
property unsigned int ID;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft ruft die ID (ein Handle) des Menüelements, Symbolleisten-Schaltfläche oder andere Benutzeroberflächen-Objekt dargestellt wird, indem die `ICommandUI` Objekt.  
  
##  <a name="index"></a>ICommandUI::Index  
 Ruft den Index des das Benutzeroberflächenobjekt, dargestellt durch die `ICommandUI` Objekt.  
  
```  
property unsigned int Index;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft ruft den Index (ein Handle) des Menüelements, Symbolleisten-Schaltfläche oder andere Benutzeroberflächen-Objekt dargestellt wird, indem die `ICommandUI` Objekt.  
  
##  <a name="radio"></a>ICommandUI::Radio  
 Legt die Benutzer-Interface-Element für diesen Befehl auf den entsprechenden Aktivierungszustand fest.  
  
```  
property bool Radio;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft legt die Benutzer-Interface-Element für diesen Befehl an den entsprechenden Aktivierungszustand. Legen Sie `Radio` auf `TRUE` So aktivieren Sie den Artikel andernfalls `FALSE`.  
  
##  <a name="text"></a>ICommandUI::Text  
 Legt den Text des Elements Schnittstelle Benutzer für diesen Befehl.  
  
```  
property String^ Text;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Eigenschaft legt den Text des Elements Schnittstelle Benutzer für diesen Befehl. Legen Sie `Text` mit einem Text-Zeichenfolge-Handle.  
  
##  <a name="iview_interface"></a>IView--Schnittstelle  
 Implementiert mehrere Möglichkeiten, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) zum Senden von Benachrichtigungen anzeigen an einem verwalteten Steuerelement verwendet.  
  
```  
interface class IView  
```  
  
### <a name="remarks"></a>Hinweise  
 `IView`mehrere Methoden implementiert, die `CWinFormsView` verwendet, um allgemeine Ansicht Benachrichtigungen zu einem gehosteten verwalteten Steuerelement weiterzuleiten. Dies sind [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) und [OnActivateView](../../mfc/reference/iview-interface.md).  
  
 `IView`ähnelt dem [CView](../../mfc/reference/cview-class.md), aber nur für verwaltete Ansichten und Steuerelemente verwendet wird.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="onactivateview"></a>IView::OnActivateView  
 Von MFC aufgerufen, wenn eine Ansicht aktiviert oder deaktiviert wird.  
  
```  
void OnActivateView(bool activate);
```  
  
### <a name="parameters"></a>Parameter  
 `activate`  
 Gibt an, ob die Sicht wird aktiviert oder deaktiviert.  
  
##  <a name="oninitialupdate"></a>IView:: OnInitialUpdate  
 Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber vor dem Beginn der Ansicht angezeigt wird.  
  
```  
void OnInitialUpdate();
```  
  
##  <a name="onupdate"></a>IView::OnUpdate  
 Vom MFC aufgerufen, nachdem die Ansicht Dokument geändert wurde.  
  
```  
void OnUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können die Ansicht, um seine Anzeige Änderungen entsprechend aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel COLLECT](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




