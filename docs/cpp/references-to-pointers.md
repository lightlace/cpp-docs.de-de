---
title: "Verweise auf Zeiger | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Referenzen, Auf Zeiger"
ms.assetid: 4ce48b08-1511-4d2f-a31f-95f99eac0c70
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Verweise auf Zeiger
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verweise auf Zeiger können nahezu auf die gleiche Weise wie Verweise auf Objekte deklariert werden.  Das Deklarieren eines Verweises auf einen Zeiger führt zu einem änderbaren Wert, der wie ein normaler Zeiger verwendet wird.  
  
## Beispiel  
 Die folgenden Codebeispiele veranschaulichen den Unterschied zwischen einem Zeiger auf einen Zeiger und einem Verweis auf einen Zeiger.  
  
 Die Funktionen `Add1` und `Add2` sind funktional äquivalent \(obwohl sie nicht auf die gleiche Weise aufgerufen werden.\)  Der Unterschied besteht darin, dass `Add1` eine doppelte Indirektion verwendet, während `Add2` die Vorteile eines Verweises auf einen Zeiger nutzt.  
  
```  
// references_to_pointers.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// STL namespace  
using namespace std;  
  
enum {  
   sizeOfBuffer = 132  
};  
  
// Define a binary tree structure.  
struct BTree {  
   char  *szText;  
   BTree *Left;  
   BTree *Right;  
};  
  
// Define a pointer to the root of the tree.  
BTree *btRoot = 0;  
  
int Add1( BTree **Root, char *szToAdd );  
int Add2( BTree*& Root, char *szToAdd );  
void PrintTree( BTree* btRoot );  
  
int main( int argc, char *argv[] ) {  
   // Usage message  
   if( argc < 2 ) {  
      cerr << "Usage: Refptr [1 | 2]" << "\n";  
      cerr << "\nwhere:\n";  
      cerr << "1 uses double indirection\n";  
      cerr << "2 uses a reference to a pointer.\n";  
      cerr << "\nInput is from stdin.\n";  
      return 1;  
   }  
  
   char *szBuf = new char[sizeOfBuffer];  
   if (szBuf == NULL) {  
      cerr << "Out of memory!\n";  
      return -1;  
   }  
  
   // Read a text file from the standard input device and  
   //  build a binary tree.  
   //while( !cin.eof() )   
   {  
      cin.get( szBuf, sizeOfBuffer, '\n' );  
      cin.get();  
  
      if ( strlen( szBuf ) ) {  
         switch ( *argv[1] ) {  
            // Method 1: Use double indirection.  
            case '1':  
               Add1( &btRoot, szBuf );  
               break;  
            // Method 2: Use reference to a pointer.  
            case '2':  
               Add2( btRoot, szBuf );  
               break;  
            default:  
               cerr << "Illegal value '"  
                  << *argv[1]  
                  << "' supplied for add method.\n"  
                     << "Choose 1 or 2.\n";  
               return -1;  
         }  
      }  
   }  
   // Display the sorted list.  
   PrintTree( btRoot );  
}  
  
// PrintTree: Display the binary tree in order.  
void PrintTree( BTree* MybtRoot ) {  
   // Traverse the left branch of the tree recursively.  
   if ( btRoot->Left )  
      PrintTree( btRoot->Left );  
  
   // Print the current node.  
   cout << btRoot->szText << "\n";  
  
   // Traverse the right branch of the tree recursively.  
   if ( btRoot->Right )  
      PrintTree( btRoot->Right );  
}  
  
// Add1: Add a node to the binary tree.  
//       Uses double indirection.  
int Add1( BTree **Root, char *szToAdd ) {  
   if ( (*Root) == 0 ) {  
      (*Root) = new BTree;  
      (*Root)->Left = 0;  
      (*Root)->Right = 0;  
      (*Root)->szText = new char[strlen( szToAdd ) + 1];  
      strcpy_s((*Root)->szText, (strlen( szToAdd ) + 1), szToAdd );  
      return 1;  
   }  
   else {  
      if ( strcmp( (*Root)->szText, szToAdd ) > 0 )  
         return Add1( &((*Root)->Left), szToAdd );  
      else  
         return Add1( &((*Root)->Right), szToAdd );  
   }  
}  
  
// Add2: Add a node to the binary tree.  
//       Uses reference to pointer  
int Add2( BTree*& Root, char *szToAdd ) {  
   if ( Root == 0 ) {  
      Root = new BTree;  
      Root->Left = 0;  
      Root->Right = 0;  
      Root->szText = new char[strlen( szToAdd ) + 1];  
      strcpy_s( Root->szText, (strlen( szToAdd ) + 1), szToAdd );  
      return 1;  
   }  
   else {  
      if ( strcmp( Root->szText, szToAdd ) > 0 )  
         return Add2( Root->Left, szToAdd );  
      else  
         return Add2( Root->Right, szToAdd );  
   }  
}  
```  
  
  **Verwendung: Refptr \[1 &#124; 2\]**  
**Dabei gilt:**  
**1 verwendet doppelte Dereferenzierung**  
**2 verwendet Verweis auf einen Zeiger.  Die Eingabe ist von stdin.**    
## Siehe auch  
 [Verweise](../cpp/references-cpp.md)