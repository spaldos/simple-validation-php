# simple-validation-php
A some basic rules for validating form input.

Example:

    $validate = new SimpleValidation(
      $input, 
      array(
        'title'       => 'required|in:Mr,Mrs',
        'firstname'   => 'required|alphanum|min:2|max:40',
        'lastname'    => 'required|alphanum|min:2|max:40',
        'dateofbirth' => 'required|date',
        'city'        => 'required|alphanum|min:2|max:30',
        'zipcode'     => 'required|number',
        'email'       => 'required|email',
        'phone'       => 'required|telephone',
        'iban'        => 'required|iban',
        'isAwesome'   => 'required|boolean'
      )
    );
    
    if($validate->failed())
    {
      print_r($validate->errors);
    }
    else
    {
      echo 'Passed, yay!';
    }
