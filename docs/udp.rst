.. _udp:


.. currentmodule:: pyuv


==============================
:py:class:`UDP` --- UDP handle
==============================


.. py:class:: UDP(loop)

    :type loop: :py:class:`Loop`
    :param loop: loop object where this handle runs (accessible through :py:attr:`UDP.loop`).

    The ``UDP`` handle provides asynchronous UDP functionallity both as a client and server.

    .. py:method:: bind((ip, port))

        :param string ip: IP address to bind to.

        :param int port: Port number to bind to.

        Bind to the specified IP address and port. This function needs to be called always,
        both when acting as a client and as a server. It sets the local IP address and port
        from which the data will be sent.

    .. py:method:: close([callback])

        :param callable callback: Callback to be called after the handle has been closed.

        Close the ``UDP`` handle. After a handle has been closed no other
        operations can be performed on it.

        Callback signature: ``callback(udp_handle)``.

    .. py:method:: send(data, [callback])

        :param string data: Data to be sent over the ``UDP`` connection.

        :param callable callback: Callback to be called after the send operation
            has been performed.

        Send data over the ``UDP`` connection.

        Callback signature: ``callback(udp_handle, status)``.

    .. py:method:: start_recv(callback)

        :param callable callback: Callback to be called when data is received on the
            bount IP address and port.

        Start receiving data on the bound IP address and port.

        Callback signature: ``callback(udp_handle, (ip, port), data)``.

    .. py:method:: stop_recv

        Stop receiving data.

