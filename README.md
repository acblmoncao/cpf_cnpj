# CPF/CNPJ

This gem does some [CPF](http://en.wikipedia.org/wiki/Cadastro_de_Pessoas_F%C3%ADsicas)/[CNPJ](http://en.wikipedia.org/wiki/CNPJ) magic. It allows you to create, validate and format CPF/CNPJ, even through the command-line.

Just making my life easier when filling these damn numbers on internet bankings and government sites.

## Installation

Add this line to your application's Gemfile:

    gem "cpf_cnpj"

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install cpf_cnpj

## Usage

### Ruby API

This library has the same API for both CNPJ/CPF, so only one of them is documented below.

    require "cpf_cnpj"

    CPF.valid?(number)    # Check if a CPF is valid
    CPF.generate          # Generate a random CPF number

    cpf = CPF.new(number)
    cpf.formatted         # Return formatted CPF (xxx.xxx.xxx-xx)
    cpf.stripped          # Return stripped CPF (xxxxxxxxxxx)
    cpf.valid?            # Check if CPF is valid

### Command-line

This library gives you two binaries: `cpf` and `cnpj`.

    $ cpf --check 532.820.857-96
    $ $?
    0

    $ cpf --check 53282085796
    $ $?
    0

    $ cpf --format 53282085796
    532.820.857-96

    $ cpf --strip 532.820.857-96
    53282085796

    $ cpf --generate
    417.524.931-17

    $ cpf --generate --strip
    76001454809

    $ echo 76001454809 | cpf -f
    760.014.548-09

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am "Added some feature"`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
