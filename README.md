xmlrpc-client
=============

An XmlRpc client with NULL support, plus a wrapper to support multiple endpoints

usage
=====

To use this client, include our autoloader, register it and create a client instance:

    require('/PATH/TO/OpenReact_XmlRpc_Client/library/OpenReact/Autoload.php');
    OpenReact_Autoload::register();

    $client = new OpenReact_XmlRpc_Client('https://URL.TO/ENDPOINT');
    var_dump($client->call('system.listMethods'));

Or, to use our client with multiple endpoints (and authentication) you can use our ServicesClient, which wraps the client:

    require('/PATH/TO/OpenReact_XmlRpc_Client/library/OpenReact/Autoload.php');
    OpenReact_Autoload::register();

    $endpoints = array(
      'https://social.react.com/XmlRpc_v2' => array('OAuthServer', 'Twitter', 'Facebook', 'Hyves', 'LinkedIn'),
      'https://share.react.com/XmlRpc_v2' => array('Share'),
    );

    $client = new OpenReact_XmlRpc_ServicesClient($endpoints, null, array('KEY', 'SECRET'));
    var_dump($client->OAuthServer->getProviders());
