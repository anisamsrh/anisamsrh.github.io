desc "Buat post baru (Contoh: rake post title=\"Judul Proyek Saya\")"
task :post do
  abort("Masukkan judul! Contoh: rake post title=\"Judul Proyek\"") unless ENV["title"]

  title = ENV["title"]
  slug = title.downcase.strip.gsub(' ', '-').gsub(/[^\w-]/, '')
  date = Time.now.strftime('%Y-%m-%d')
  filename = "_posts/#{date}-#{slug}.md"

  if File.exist?(filename)
    abort("File sudah ada!")
  end

  puts "Membuat file baru: #{filename}"
  File.open(filename, "w") do |f|
        f.puts "---"
        f.puts "layout: post"
        f.puts "title: \"#{title}\""
        f.puts "date: #{Time.now.strftime('%Y-%m-%d %H:%M:%S %z')}"
        f.puts "image: \"/assets/images/default.jpeg\""
        f.puts "description: \"Tulis deskripsi singkat proyek di sini...\""
        f.puts "github_url: \"\""
        f.puts "demo_url: \"\""
        f.puts "paper_url: \"\""
        f.puts "external_url: \"\"" # Isi jika artikel dihosting di domain lain (misal: Medium)
        f.puts "---"
        f.puts ""
        f.puts "Tulis konten proyek Anda secara lengkap di sini..."
      end
end