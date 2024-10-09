#######################
Compatibility Functions
#######################

CodeIgniter provides a set of compatibility functions that enable
you to use functions what are otherwise natively available in PHP,
but only in higher versions or depending on a certain extension.

Being custom implementations, these functions will also have some
set of dependencies on their own, but are still useful if your
PHP setup doesn't offer them natively.

.. note:: Much like the :doc:`common functions <common_functions>`, the
	compatibility functions are always available, as long as
	their dependencies are met.

.. contents::
  :local:

.. raw:: html

  <div class="custom-index container"></div>

****************
Multibyte String
****************

This set of compatibility functions offers limited support for PHP's
`Multibyte String extension <http://php.net/mbstring>`_. Because of
the limited alternative solutions, only a few functions are available.

.. note:: When a character set parameter is ommited,
	``$config['charset']`` will be used.

Dependencies
============

- `iconv <http://php.net/iconv>`_ extension

.. important:: This dependency is optional and these functions will
	always be declared. If iconv is not available, they WILL
	fall-back to their non-mbstring versions.

.. important:: Where a character set is supplied, it must be
	supported by iconv and in a format that it recognizes.

.. note:: For you own dependency check on the actual mbstring
	extension, use the ``MB_ENABLED`` constant.

Function reference
==================

.. php:function:: mb_strlen($str[, $encoding = NULL])

	:param	string	$str: Input string
	:param	string	$encoding: Character set
	:returns:	Number of characters in the input string or FALSE on failure
	:rtype:	string

	For more information, please refer to the `PHP manual for
	mb_strlen() <http://php.net/mb_strlen>`_.

.. php:function:: mb_strpos($haystack, $needle[, $offset = 0[, $encoding = NULL]])

	:param	string	$haystack: String to search in
	:param	string	$needle: Part of string to search for
	:param	int	$offset: Search offset
	:param	string	$encoding: Character set
	:returns:	Numeric character position of where $needle was found or FALSE if not found
	:rtype:	mixed

	For more information, please refer to the `PHP manual for
	mb_strpos() <http://php.net/mb_strpos>`_.

.. php:function:: mb_substr($str, $start[, $length = NULL[, $encoding = NULL]])

	:param	string	$str: Input string
	:param	int	$start: Position of first character
	:param	int	$length: Maximum number of characters
	:param	string	$encoding: Character set
	:returns:	Portion of $str specified by $start and $length or FALSE on failure
	:rtype:	string

	For more information, please refer to the `PHP manual for
	mb_substr() <http://php.net/mb_substr>`_.
