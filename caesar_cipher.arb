require 'pry-byebug'

def caesar_cipher(string,positions)
    array = string_to_letters(string)
    new_word =""
    for i in 0..array.length-1
        letter =  array[i].to_s
        if letter.is_upper?
            new_word << move_a_to_z_upper(letter,positions)
        else
            new_word << move_a_to_z_down(letter,positions)
        end
    end
    puts "Sua nova palavra é #{new_word}"
end

# Move as posições das palavras maiusculas
def move_a_to_z_upper(letter,positions)
    dicionario = []
    for i in "A".ord.."Z".ord
        dicionario.push(i.chr)
    end

    if !dicionario.include?(letter)
        letter
    elsif dicionario.index(letter) <= (dicionario.length-1 - positions)
        letter = dicionario[dicionario.index(letter) + positions]
    else
        letter = dicionario[dicionario.index(letter)+ positions - 26]
    end
end


# Move as posições das palavras minusculas
def move_a_to_z_down(letter,positions)
    dicionario = []
    for i in "a".ord.."z".ord
        dicionario.push(i.chr)
    end

    if !dicionario.include?(letter)
        letter
    elsif dicionario.index(letter) <= dicionario.length-1 - positions
        letter = dicionario[dicionario.index(letter) + positions]
    else
        letter = dicionario[dicionario.index(letter)+ positions - 26]
    end
end

# Transforma a palavra digitada em um array com as strings
def string_to_letters(string)
    palavra = []
    string.each_char {|char| palavra.push(char)}
    return palavra
end

# Checa se a letra é maiuscula/minuscula
class String
    def is_upper?
      self == self.upcase
    end
  
    def is_lower?
      self == self.downcase
    end
end

# Teste
caesar_cipher("Abc Defg HijSADSA>>",5)