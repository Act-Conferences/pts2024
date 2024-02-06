# Resizing

Pipe to sh(1) when you're sure the commands are correct.

    mkdir new
    for f in *.jpg; do echo echo $f \; convert $f -resize 800x new/$f-800x \; ; done

    cd new
    for f in *-800x; do echo mv $f ${f/.jpg-800x/}-\$\(identify $f \| awk \''{print $3}'\'\).jpg \; ; done


