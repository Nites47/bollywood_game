#Bollywood
file = 'E:\Python\indian_movies.csv'
data = pd.read_csv(file)
#data.head()
movielist=data['Movie Name'].tolist()

# function to convert to superscript
def get_super(x):
    normal = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+-=()"
    super_s = "ᴬᴮᶜᴰᴱᶠᴳᴴᴵᴶᴷᴸᴹᴺᴼᴾ۹ᴿˢᵀᵁⱽᵂˣʸᶻᵃᵇᶜᵈᵉᶠᵍʰᶦʲᵏˡᵐⁿᵒᵖ۹ʳˢᵗᵘᵛʷˣʸᶻ⁰¹²³⁴⁵⁶⁷⁸⁹⁺⁻⁼⁽⁾"
    res = x.maketrans(''.join(normal), ''.join(super_s))
    return x.translate(res)

def strike(text):
    return ''.join([u'\u0336{}'.format(c) for c in text])

def game():
    movie=rn.choice(movielist).upper()
    alphabet=set(st.ascii_uppercase+st.digits)
    used_letter=set(' '+st.punctuation)
    movie_letters=set(movie)-used_letter
    b='bollywood'
    life=len(b)
    while len(movie_letters)>0 and life>0:
        print(b)
        word=[i if i in used_letter else '-' for i in movie]
        print('Current word :',''.join(word))
        letter=input('Guess a letter:').upper()
        if letter in alphabet - used_letter:
            used_letter.add(letter)
            if letter in movie_letters:
                movie_letters.remove(letter)
            else:
                b=''.join(b[i] if i!=len(b)-life else strike(b[i])+get_super(letter) for i in range(len(b)))
                life=life-1
        elif letter in used_letter:
            print('You have already used the letter')
        else:
            print('enter valid letter')
    if(life==0):
        print(f'Sorry you are out of life. The movie is {movie}')
    else:
        print(f'Congrats you have guessed the movie correctly. It\'s {movie}')
game()
