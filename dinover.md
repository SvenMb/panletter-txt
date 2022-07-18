	John Doe
	42 main Street
J. Doe, 42 main Street, 12345 Anytown	12345 Anytown
	USA
	+1 555 56789

	$if(invoice)$$if(invoicename)$$invoicename$$else$Re:$endif$ $invoice$$endif$
	$if(myref)$$if(myrefname)$$myrefname$ $endif$$myref$$endif$
	$if(yourref)$$if(yourrefname)$$yourrefname$ $endif$$yourref$$endif$
