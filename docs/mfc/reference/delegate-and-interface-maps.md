---
title: Delegaten und der Schnittstelle zugeordnet werden Makros (MFC) | Microsoft Docs
ms.custom: 
ms.date: 03/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
caps.latest.revision: "1"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b30586116fff517818822f484b1285a59fd2a98b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
|||  
|-|-|  
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Startet eine Karte Delegaten an.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|Die Definition der Zuordnung interfaced beginnt.|
|[CommandHandler-Delegat](#commandhandler)|Registriert eine Befehlsquelle Rückrufmethoden.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Eine Delegat-Zuordnung wird beendet.|
|[END_INTERFACE_MAP](#end_interface_map)|Beendet die schnittstellenzuordnung in der Implementierungsdatei. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Erstellt einen Eintrag in der Zuordnung des Delegaten an.|
|[INTERFACE_PART](#interface_part)|Wird zwischen der `BEGIN_INTERFACE_MAP` Makros und die `END_INTERFACE_MAP` -Makro für jede Schnittstelle, die dem Objekt unterstützt wird.|
|[MAKE_DELEGATE](#make_delegate)|Fügt einen Ereignishandler zu einem verwalteten-Steuerelement.|


## <a name="begin_delegate_map"></a>BEGIN_DELEGATE_MAP
Startet eine Karte Delegaten an.  
   
### <a name="syntax"></a>Syntax    
```  
BEGIN_DELEGATE_MAP(  CLASS );  
```
### <a name="parameters"></a>Parameter  
 `CLASS`  
 Die Klasse, in der das verwaltete Steuerelement gehostet wird.  
   
### <a name="remarks"></a>Hinweise  
 Dieses Makro kennzeichnet den Anfang einer Liste von Delegaten Einträgen, die eine Zuordnung Delegaten bilden. Ein Beispiel, wie dieses Makro verwendet wird, finden Sie unter [EVENT_DELEGATE_ENTRY](#event_delegate_entry).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** msclr\event.h  
   
### <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus nativen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)
 
##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP
Beginn der Definition der interfaced Zuordnung, wenn Sie in der Implementierungsdatei verwendet.  
   
### <a name="syntax"></a>Syntax    
```
BEGIN_INTERFACE_MAP( theClass, baseClass )  
```
### <a name="parameters"></a>Parameter  
 `theClass`  
 Die Klasse, in der die Schnittstellenzuordnung definiert werden soll  
  
 `baseClass`  
 Die Klasse, von der `theClass` abgeleitet wird.  
   
### <a name="remarks"></a>Hinweise  
 Für jede Schnittstelle, die implementiert wird, besteht eine oder mehrere `INTERFACE_PART` -Makroaufrufe. Für jedes Aggregat, das die Klasse verwendet wird, ist eine **INTERFACE_AGGREGATE** Makroaufruf.  
  
 Weitere Informationen zu schnittstellenzuordnungen, finden Sie unter [technischen Hinweis 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
 
##  <a name="commandhandler"></a>CommandHandler-Delegat
Registriert eine Befehlsquelle Rückrufmethoden.  
   
### <a name="syntax"></a>Syntax    
```  
delegate void CommandHandler(  UINT^ cmdID  );  
```
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
   
### <a name="remarks"></a>Hinweise  
 Dieser Delegat wird mit einem Befehl Rückrufmethoden registriert. Wenn Sie einen Delegaten mit dem Befehlsquellobjekt hinzufügen, wird die Rückrufmethode einen Handler für Befehle, die aus der angegebenen Quelle stammen.  
  
 Weitere Informationen finden Sie unter [wie: Hinzufügen Befehlsrouting zum Windows Forms-Steuerelements](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  
   
### <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Hinzufügen von Befehlsrouting zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)
 
##  <a name="commanduihandler"></a>CommandUIHandler
Registriert Rückrufmethoden mit einer benutzermeldung Schnittstelle Update-Befehl.  
   
### <a name="syntax"></a>Syntax    
```  
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);  
```
### <a name="parameters"></a>Parameter  
 `cmdID`  
 Die Befehls-ID.  
  
 `cmdUI`  
 Die Befehls-ID.  
   
### <a name="remarks"></a>Hinweise  
 Dieser Delegat registriert Rückrufmethoden mit einer benutzermeldung Schnittstelle Update-Befehl. `CommandUIHandler`ähnelt dem [CommandHandler](#commandhandler) mit dem Unterschied, dass dieser Delegat mit Benutzer-Schnittstelle Objekt Update-Befehle verwendet wird. Benutzeroberflächenbefehlen Update sollte 1: 1 mit Ereignishandlermethoden Nachricht zugeordnet werden.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  
   
### <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Hinzufügen (Befehl) Befehlsrouting zum Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [CommandHandler](#commandhandler)

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP
Eine Delegat-Zuordnung wird beendet.  
   
### <a name="syntax"></a>Syntax    
```  
END_DELEGATE_MAP();  
```  
   
### <a name="remarks"></a>Hinweise  
 Dieses Makro markiert das Ende einer Liste von Delegaten Einträgen, die eine Zuordnung Delegaten bilden. Ein Beispiel, wie dieses Makro verwendet wird, finden Sie unter [EVENT_DELEGATE_ENTRY](#event_delegate_entry).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** msclr\event.h  
   
### <a name="see-also"></a>Siehe auch  

 [Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus nativen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

 
##  <a name="end_interface_map"></a>END_INTERFACE_MAP
Beendet die schnittstellenzuordnung in der Implementierungsdatei.  
   
### <a name="syntax"></a>Syntax    
```
END_INTERFACE_MAP( )    
```  
   
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu schnittstellenzuordnungen, finden Sie unter [technischen Hinweis 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [BEGIN_INTERFACE_MAP](#begin_interface_map)
 

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY
Erstellt einen Eintrag in der Zuordnung des Delegaten an.  
   
### <a name="syntax"></a>Syntax    
```  
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);  
```
### <a name="parameters"></a>Parameter  
 `MEMBER`  
 Die Ereignishandlermethode, die an das Steuerelement angefügt werden.  
  
 `ARG0`  
 Das erste Argument der verwalteten Ereignishandlermethode, z. B. **Object ^**.  
  
 `ARG1`  
 Das zweite Argument der verwalteten Ereignishandlermethode, z. B. **EventArgs ^**.  
   
### <a name="remarks"></a>Hinweise  
 Jeder Eintrag in der Zuordnung des Delegaten entspricht einem verwalteten Ereignishandlerdelegaten erstellt, indem [MAKE_DELEGATE](#make_delegate).  
   
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie `EVENT_DELEGATE_ENTRY` So erstellen einen Eintrag in der Zuordnung der Delegat für die `OnClick` Ereignishandler; Siehe auch das Codebeispiel in `MAKE_DELEGATE`. Weitere Informationen finden Sie unter [wie: Auffangen von Windows Forms-Ereignissen aus systemeigenen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).  
  
 ```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()

```  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** msclr\event.h  
   
### <a name="see-also"></a>Siehe auch  
 [MAKE_DELEGATE](#make_delegate)   
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)
 

##  <a name="interface_part"></a>INTERFACE_PART
Wird zwischen der `BEGIN_INTERFACE_MAP` Makros und die `END_INTERFACE_MAP` -Makro für jede Schnittstelle, die dem Objekt unterstützt wird.  
   
### <a name="syntax"></a>Syntax    
```
INTERFACE_PART( theClass, iid, localClass)  
```
### <a name="parameters"></a>Parameter  
 `theClass`  
 Der Name der Klasse, die die Schnittstellenzuordnung enthält.    
 `iid`  
 Die IID, die der eingebetteten Klasse zugeordnet werden.    
 *localClass*  
 Der Name der lokalen Klasse.  
   
### <a name="remarks"></a>Hinweise  
 Sie können Sie eine IID auf einen Member der Klasse, die durch zuordnen `theClass` und *LocalClass*.  
  
 Weitere Informationen zu schnittstellenzuordnungen, finden Sie unter [technischen Hinweis 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
   
 
##  <a name="make_delegate"></a>MAKE_DELEGATE
Fügt einen Ereignishandler zu einem verwalteten-Steuerelement.  
   
### <a name="syntax"></a>Syntax    
```  
MAKE_DELEGATE( DELEGATE,  MEMBER) ;  
```
### <a name="parameters"></a>Parameter  
 `DELEGATE`  
 Der Typ des verwalteten-ereignishandlers zu delegieren, z. B. [EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True).  
  
 `MEMBER`  
 Der Name der Ereignishandlermethode an das Steuerelement angefügt werden.  
   
### <a name="remarks"></a>Hinweise  
 Dieses Makro erstellt einen verwaltetes Ereignishandlerdelegaten des Typs `DELEGATE` und des Namens `MEMBER`. Die verwalteten Ereignishandlerdelegaten ermöglicht eine systemeigene Klasse verwaltete Ereignisse zu behandeln.  
   
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Aufrufen `MAKE_DELEGATE` Anfügen einer `OnClick` -Ereignishandler zu einem MFC-Steuerelement `MyControl`. Eine umfassendere Erläuterung zur Funktionsweise dieses Makro in einer MFC_Anwendung finden Sie unter [wie: Auffangen von Windows Forms-Ereignissen aus systemeigenen C++-Klassen](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).  
  
```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```
   
### <a name="requirements"></a>Anforderungen  
 **Header:** msclr\event.h  
   
### <a name="see-also"></a>Siehe auch  
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)
 



